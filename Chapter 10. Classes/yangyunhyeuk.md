## 10장 클래스

---

### 클래스는 작아야 한다.

- 클래스를 만들 때 가장 중요한 규칙은 크기이다.
    - 함수와 마찬가지로 클래스는 ‘작게’가 기본 규칙이라는 의미이다.
    - 그렇다면 함수는 물리적인 행의 수로 크기를 측정했으나, 클래스는 어떤 척도를 사용할까
        - 그것은 책임이다. (단일 책임 원칙)
            - 클래스는 책임, 즉 변경할 이유가 하나여야 한다.
        - 허나 우리는 수많은 책임을 떠안은 클래스를 꾸준하게 접한다.
            - 도구 상자를 어떻게 관리하고 싶은가?
                1. 작은 서랍을 많이 두고 기능과 이름이 명확한 컴포넌트를 나눈다.
                2. 큰 서랍 몇 개를 두고 모두를 던져넣는다. 
- 클래스 이름에 Processor, Manager, Super 등 모호한 단어가 있다면 그것은 클래스에다가 여러 책임을 떠넘겼다는 의미이다.
    - 나도 생각해보니, 서비스 클래스 내 함수명을 모호하게 정하여 많은 역할을 떠넘긴건 아닌지 뒤돌아보게되었다.
- 큰 클래스 몇 개가 아니라 작은 클래스 여럿으로 이뤄진 시스템이 더 바람직하다.
    - 작은 클래스는 각자 맡은 책임이 하나며 변경할 이유가 하나며 다른 작은 클래스와 협력해 시스템에 필요한 동작을 수행한다.
- 응집도
    - 일반적으로 메서드가 변수를 더 많이 사용할수록 메서드와 클래스는 응집도가 더 높다.
    - 모든 인스턴스 변수를 메서드마다 사용하는 클래스는 응집도가 가장 높다.
    - 응집도가 높다는 말은 클래스에 속한 메서드와 변수가 서로 의존하며 논리적인 단위로 묶인다는 의미이다.
    - 응집도가 높아질수록 변수와 메서드를 적절히 분리해 새로운 클래스 2,3개로 쪼개준다.

### 리팩토링을 수행한 코드

- 가장 먼저 눈에 띄게 될 변화는 코드가 길어진다는 사실이다.
    1. 리팩토링한 프로그램은 좀 더 길고 서술적인 변수 이름을 사용한다. 
    2. 리팩토링한 프로그램은 코드에 주석을 추가하는 수단으로 함수 선언과 클래스 선언을 활용한다. 
    3. 가독성을 높이고자 공백을 추가하고 형식을 맞춘다. 

### 변경하기 쉬운 클래스

- 깨끗한 시스템은 클래스를 체계적으로 정리해 변경에 수반하는 위험이 낮다.
- OCP
    - 클래스는 확정에 개방적이고 수정에 폐쇄적이어야 한다는 원칙이다.
    - 새 기능을 수정하거나 기존 기능을 변경할 때 건드릴 코드가 최소인 시스템이 바람직하다.
- 변경으로부터 격리
    - 인터페이스 or 추상 클래스(구현에 미치는 영향을 격리하는 역할)가 아닌 상세한 구현에 의존하는 클라이언트 클래스는 구현이 바뀌면 위험에 빠진다.
    - 결합도가 낮다는 소리는 각 시스템 요소가 다른 요소로부터 그리고 변경으로부터 잘 격리되어 있다는 의미이다.
    - 시스템 요소가 서로 잘 격리되어 있으면 각 요소를 이해하기도 더 쉬워진다.
- 이렇게 결합도를 최소로 줄이면 자연스럽게 DIP 원칙을 따르는 클래스가 나온다.
    - DIP : 클래스가 상세한 구현이 아니라 추상화에 의존해야 한다는 원칙
