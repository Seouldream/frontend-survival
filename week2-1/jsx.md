# 🥯 REST API 와 GraphQL

### REST API 란?

REST API(Representational State Transfer 애플리케이션 프로그래밍 인터페이스)는 HTTP(하이퍼텍스트 전송 프로토콜) 메서드를 사용하여 클라이언트 애플리케이션과 통신하는 웹 서비스를 설계하고 구현하기 위한 아키텍처 스타일입니다. 이는 웹 서비스 설계 방식을 정의하는 일련의 제약 조건과 원칙입니다.

REST API를 사용하면 클라이언트 애플리케이션이 GET, POST, PUT, DELETE, PATCH와 같은 표준 HTTP 메서드를 사용하여 서버 리소스와 상호 작용할 수 있습니다. 이러한 메서드는 서버 리소스에 대한 CRUD(만들기, 읽기, 업데이트, 삭제) 작업에 해당합니다. 서버 리소스는 고유한 URI(Uniform Resource Identifier)로 표시되며 응답은 일반적으로 JSON(JavaScript Object Notation) 또는 XML(확장 가능한 마크업 언어) 형식입니다.

RESTful API의 주요 특징 중 하나는 클라이언트가 서버에 보내는 각 요청에 요청을 완료하는 데 필요한 모든 정보가 포함되어 있고 서버가 요청 사이에 클라이언트 세션 정보를 저장하지 않는다는 상태 비저장성(stateless)이라는 점입니다. 따라서 REST API는 확장성과 효율성이 매우 뛰어납니다.

REST API는 웹 개발에서 널리 사용되며 웹 기반 애플리케이션과 모바일 애플리케이션 간의 주요 통신 수단입니다. 웹 서비스 구축의 표준이 되었으며 대부분의 최신 프로그래밍 언어와 프레임워크에서 지원됩니다.

#### 세션?

웹 개발에서 세션은 클라이언트와 서버 간의 여러 요청과 응답에 걸쳐 사용자에 대한 상태 정보를 유지하는 데 사용되는 메커니즘입니다. 세션을 통해 서버는 로그인 정보나 기본 설정과 같은 사용자별 데이터를 저장하고 해당 데이터를 쿠키 또는 URL의 매개변수로 클라이언트에 전송되는 고유 세션 ID와 연결할 수 있습니다.

사용자가 웹사이트를 처음 방문하면 서버는 해당 사용자를 위한 새 세션을 생성하고 고유한 세션 ID를 할당합니다. 이 세션 ID는 서버에 저장되어 쿠키 또는 URL 매개변수로 클라이언트에 전송됩니다. 그러면 클라이언트는 이후 요청할 때마다 이 세션 ID를 서버로 다시 전송하여 서버가 사용자의 저장된 데이터를 검색하고 사용자에 대한 상태 저장 정보를 유지할 수 있도록 합니다.

세션은 일반적으로 로그인 자격 증명, 장바구니 항목 또는 사용자 기본 설정과 같이 비공개로 안전하게 유지해야 하는 민감한 정보를 저장하는 데 사용됩니다. 또한 세션은 서버가 사용자가 특정 리소스에 액세스할 권한이 있는지 확인할 수 있는 사용자 인증 및 권한 부여와 같은 기능을 구현하는 데 사용할 수도 있습니다.

세션은 서버에서 관리하며 일정 시간이 지나거나 사용자가 로그아웃하거나 브라우저를 닫을 때 만료되도록 구성할 수 있습니다. 세션이 손상되면 민감한 정보나 작업에 대한 무단 액세스로 이어질 수 있으므로 보안을 위해서는 적절한 세션 관리가 중요합니다.

전반적으로 세션은 웹 개발에서 중요한 부분으로, 서버가 사용자에 대한 상태 저장 정보를 유지하고 보다 개인화되고 안전한 경험을 제공할 수 있게 해줍니다.

### GraphQL 이란?

GraphQL은 Facebook에서 개발한 API(애플리케이션 프로그래밍 인터페이스)를 위한 쿼리 언어이자 런타임입니다. 클라이언트가 필요한 데이터만 요청할 수 있도록 하고 서버에 요청 중인 데이터를 명확하고 예측 가능한 방식으로 보여줌으로써 기존 REST API에 비해 더 효율적이고 강력하며 유연한 대안을 제공합니다.

GraphQL을 사용하면 클라이언트는 REST API에서 반환되는 고정된 데이터 집합을 받는 대신 필요한 데이터를 정확히 지정하고 해당 데이터만 받을 수 있습니다. 따라서 네트워크를 통해 전송되는 불필요한 데이터의 양이 줄어들어 성능이 향상되고 클라이언트 측 코드의 복잡성이 줄어듭니다.

GraphQL의 또 다른 주요 기능은 단일 쿼리에서 여러 소스의 데이터를 확인할 수 있다는 것입니다. 이를 통해 클라이언트는 여러 데이터베이스 또는 마이크로서비스에서 데이터를 가져오는 경우에도 요청하는 데이터를 완전하고 일관성 있게 볼 수 있습니다.

또한 GraphQL은 요청 및 반환되는 데이터의 구조를 정의하는 강력한 형식의 스키마를 제공합니다. 이 스키마는 런타임에 쿼리의 유효성을 검사하는 데 사용되어 유효한 쿼리만 실행되도록 보장하고 런타임 오류의 가능성을 줄입니다.

전반적으로 GraphQL은 성능을 개선하고 복잡성을 줄이며 더 나은 개발자 경험을 제공할 수 있는 API를 구축하기 위한 강력하고 유연한 도구입니다.

### GraphQL은 왜 등장했는가?

GraphQL은 기존 REST API의 몇 가지 한계를 해결하기 위해 2012년에 Facebook에서 개발했습니다. GraphQL의 개발은 Facebook의 모바일 애플리케이션에서 데이터를 쿼리하고 조작하는 보다 효율적이고 유연한 방법에 대한 필요성에 의해 주도되었습니다.

GraphQL의 첫 번째 버전은 Facebook의 내부 프로젝트로 개발되었으며, 모바일 애플리케이션을 구동하는 데 사용되었습니다. 시간이 지남에 따라 GraphQL의 이점이 분명해졌고, 결국 2015년에 오픈 소스 프로젝트로 출시되었습니다.

출시 이후 GraphQL은 많은 인기를 얻었으며 현재 많은 회사에서 API를 구축하는 데 사용하고 있습니다. GraphQL의 개발은 이제 개발자와 기업 커뮤니티가 주도하고 있으며, 이들은 GraphQL의 발전과 진화에 기여하고 있습니다.

GraphQL 사양은 GraphQL의 개발과 거버넌스를 감독하는 독립적인 조직인 GraphQL 재단에서 유지 관리합니다. 이 재단은 GraphQL 커뮤니티와 협력하여 API 구축을 위한 표준으로 GraphQL을 개발하고 홍보합니다.

### REST API vs GraphQL

REST API와 GraphQL은 모두 API를 구축하는 데 사용되지만, 작동 방식과 최적화 대상 측면에서 몇 가지 근본적인 차이점이 있습니다.

REST API는 HTTP 메서드를 사용하여 서버 리소스에서 CRUD 작업을 수행하는 웹 서비스를 구축하기 위한 아키텍처 스타일입니다. REST API는 미리 정의된 형식(일반적으로 JSON 또는 XML)으로 데이터를 반환하는 고정된 엔드포인트 집합을 기반으로 합니다. REST API는 간단하고 예측 가능한 구조가 필요하며 클라이언트가 고정된 리소스 집합에 액세스해야 하는 API를 구축하는 데 가장 적합합니다.

반면 GraphQL은 클라이언트가 필요한 데이터만 요청할 수 있고 서버에 요청 중인 데이터에 대한 명확하고 예측 가능한 보기를 제공하는 API를 구축하기 위한 쿼리 언어 및 런타임입니다. GraphQL API는 요청 및 반환되는 데이터의 구조를 정의하는 스키마를 기반으로 합니다. GraphQL API는 데이터가 매우 가변적이고 클라이언트가 여러 소스의 데이터에 액세스해야 하는 API를 구축하는 데 가장 적합합니다.

다음은 REST API와 GraphQL의 몇 가지 주요 차이점입니다:

데이터 가져오기: REST API에서는 각 엔드포인트가 고정된 데이터 집합을 반환하는 반면, GraphQL에서는 클라이언트가 필요한 데이터를 정확히 지정하고 해당 데이터만 가져올 수 있습니다. 따라서 일부 데이터만 필요한 복잡한 쿼리에서 GraphQL이 더 효율적입니다.

엔드포인트 구조: REST API는 미리 정의된 형식으로 데이터를 반환하는 고정된 엔드포인트 집합을 가지고 있는 반면, GraphQL API는 클라이언트가 어떤 데이터 조합이든 요청할 수 있는 유연한 구조를 가지고 있습니다.

데이터 유효성 검사: REST API는 HTTP 상태 코드를 사용하여 오류를 표시하는 반면, GraphQL은 강력하게 유형화된 스키마를 사용하여 런타임에 쿼리의 유효성을 검사하여 유효한 쿼리만 실행되도록 보장합니다.

전반적으로 REST API와 GraphQL 모두 고유한 장단점이 있으며, 둘 중 어떤 것을 선택할지는 프로젝트의 특정 요구 사항에 따라 달라집니다. API 요구 사항이 간단하고 예측 가능한 경우 REST API가 최선의 선택일 수 있습니다. 그러나 데이터 요구 사항이 복잡하고 가변적이라면 GraphQL이 더 적합할 수 있습니다.