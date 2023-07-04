# Wasm (WebAssembly)

#
# 1. Keywords
- Binary Instruction Format
- Execution in Web browser
- Preformance
- JS Integration
- language interoperability
  
#
# 2. intro
Wasm은 stack 기반 가상 머신을 위한 바이너리 명령어 형식이다.
C, CPP, Rust와 같은 고급 언어 컴파일을 위한 이식 가능한 타깃으로 설계되어 client, server 어플리케이션을 web에 배포할 수 있다.

#
# 3. How it Works

1. Compilation
C, CPP, Rust로 쓰인 코드가 wasm 바이트코드로 컴파일 됨.

2. Loading in browser
컴파일된 bytecode는 모던 웹 브라우저에서 load, 실행된다.

3. Integration w/ JS
Wasm 모듈은 import 되어 JS code에서 사용될 수 있다. 이 부분이 어플리케이션의 성능에 큰 영향을 준다. (e.g. game, image processing)

4. Security and Sandboxing
코드는 **&&`sandboxed` 실행 환경에서 실행된다. (JS의 작동 방식과 비슷함) 이는 host system으로부터의 안전과 고립을 보장한다.

#
# 4. Use case
1. Preformance-Intensive Web Application
게임, **&&CAD application, 이미지/비디오 편집 등의 경우에서 wasm는 일반적인 하드웨어 기능을 활용해 native에 가까운 속도를 실행할 수 있다.

2. Code Reuse and Portability
존재하는 C, CPP 라이브러리나 컴포넌트를 web application에서 재사용할 수 있다.

3. Language Interoperability
Webassembly를 사용해 appl의 성능에 중요한 구성 요소를 rust, C, CPP같은 언어로 작성하고, 이런 구성 요소를 JS로 작성된 appl의 나머지 부분과 원활하게 통합할 수 있다.

#
# 5. Practical Example
이미지 편집 appl를 생각해보자. 필터, 변형등의 이미지 처리 과정은 계싼적으로 비싸고, JS로 구현한다면 느리다.

이런 부분을 CPP나 rust로 작성하고, wasm으로 컴파일하면 브라우저에서 native에 준하는 속도를 구동할 수 있다. 이는 성능 향상뿐만아니라 코드의 재활용도 가능케 한다. (특히 cpp, rust로 작성된 라이브러리가 있는 경우)

#
# 6. ref
- official docu : https://webassembly.org/
- mozila docu : https://developer.mozilla.org/en-US/docs/WebAssembly
