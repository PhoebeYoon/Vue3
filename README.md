# Vue3 Lesson 를 위한 용어 예습

1. Creation : 컴포넌트 초기화
2. Mounting : Dom 작성
3. Updating : 상태 변화로 인한 렌더링
4. Destruction : 소멸
5. new Vue로 선언하여 만들어진 객체를 vue 인스턴스라고 한다
6. el : 태그에 지정한 ID, 클래스명, 태그명으로 해당 태그와 vue 인스턴스를 연결
7. data : key와 value를 지정하는 json형식으로 데이터 입력 옵션
8. computed : getter/setter를 지정하는 옵션
9. rendering : 화면에 표시할 내용을 만드는 과정으로 웹브라우저는 우리가 어떤 사이트를 방문하거나 웹페이지를 바꿀때마다 렌더링이라는 절차를 거쳐서 우리에게 해당 페이지를 보여주는 것이다. 렌더링과정에는 DOM를 생성하고 csssom를 결합하여 렌더링 트리라는 것을 형성합니다. 그리고 각 노드의 위치와 크기를 계산하고 노드를 화면에 그립니다 (이것을 페인팅 또는 래스터화라고 한다). 사용자의 요구에 의해 위치와 내용이 바뀌면 리플로우, 리페인트가 발생합니다.  
* 렌더링 메카리즘 : Vue는 어떻게 템플릿을 가져와 실제 DOM 노드로 변환할까, Vue는 이러한 DOM 노드를 어떻게 효율적으로 업데이트합니까? 여기서는 Vue의 내부 렌더링 메커니즘을 살펴봐야 합니다.  
* Vue의 렌더링 시스템은 '가상 DOM'이라는 것을 기반으로 한다. 가상 DOM은 메모리에 내용을 갖고 있다가 실제 DOM에 동기화하는 프로그램 기법이다.
10. data: { Vue 객체에서 사용할 데이터들을 정의한다. 대부분 'key-value' 형식의 JSON 형태로, 여러 개를 동시에 명시할 수 있다.}
11. methods:{ Vue 객체에서 사용할 함수들을 명시한다. data와 마찬가지로 여러 개의 함수를 동시에 명시할 수 있다.}
