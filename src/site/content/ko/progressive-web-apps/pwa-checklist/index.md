---
layout: post
title: 무엇이 좋은 프로그레시브 웹 앱을 만드는가?
authors:
  - samrichard
  - petelepage
date: 2020-01-06
updated: 2020-02-24
description: |2

  무엇이 좋은 또는 훌륭한 프로그레시브 웹 앱을 만드는가?
tags:
  - progressive-web-apps
---

<!-- Disable heading-increment because it mucks with the Details widget -->

<!--lint disable heading-increment-->

프로그레시브 웹 앱(PWA)은 최신 API로 구축 및 향상되어 단일 코드베이스로 *누구에게나 어디서나 모든 장치에 도달하면서 향상된 기능, 안정성 및 설치 가능성을 제공합니다.* 최상의 경험을 만드는 데 도움이 되도록 [핵심](#core) 및 [최적](#optimal)의 체크리스트와 권장 사항을 사용하여 안내하십시오.

## 핵심 프로그레시브 웹 앱 체크리스트 {: #core }

프로그레시브 웹 앱 체크리스트는 크기나 입력 유형에 관계없이 모든 사용자가 앱을 설치하고 사용할 수 있도록 하는 요소를 설명합니다.

{% Details %} {% DetailsSummary 'h3' %}

빠르게 시작하고 빠르게 유지

성능이 좋은 사이트는 성능이 떨어지는 사이트보다 사용자를 더 잘 참여시키고 유지하기 때문에 성능은 모든 온라인 경험의 성공에 중요한 역할을 합니다. 사이트는 사용자 중심의 성능 측정항목을 최적화하는 데 중점을 두어야 합니다.

{% endDetailsSummary %}

성능이 좋은 사이트는 성능이 저조한 사이트보다 사용자를 더 잘 참여시키고 유지하기 때문에 성능은 모든 온라인 경험의 성공에 중요한 역할을 합니다. 사이트는 사용자 중심의 성능 측정항목을 최적화하는 데 중점을 두어야 합니다.

#### 이유

사용자가 앱을 *사용*하도록 하려면 속도가 중요합니다. 실제로 페이지 로드 시간이 1초에서 10초로 늘어나면 사용자가 이탈할 확률은 123% 증가합니다. 성능은 `load` 이벤트에서 그치지 않습니다. 사용자는 버튼 클릭과 같은 상호 작용이 입력되었는지 여부를 궁금해해서는 안 됩니다. 스크롤과 애니메이션이 부드럽게 느껴져야 합니다. 성능은 사용자가 애플리케이션을 인식하는 방식에서 실질적인 성능에 이르기까지 전체 경험에 영향을 줍니다.

모든 응용 프로그램의 요구 사항은 다르지만 Lighthouse의 성능 감사는 [RAIL 사용자 중심 성능 모델을](https://developers.google.com/web/fundamentals/performance/rail) 기반으로 하며 이러한 감사에서 높은 점수를 받으면 사용자가 즐거운 경험을 할 가능성이 높아집니다. [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/) 또는 [Chrome 사용자 경험 보고서](https://developers.google.com/web/tools/chrome-user-experience-report/)를 사용하여 웹 앱에 대한 실제 성능 데이터를 얻을 수도 있습니다.

#### 방법

[빠른 로드 시간](/fast/)에 대한 가이드를 따라 PWA를 빠르게 시작하고 빠르게 유지하는 방법을 알아보세요.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

모든 브라우저에서 작동

사용자는 웹 앱을 설치하기 전에 선택한 모든 브라우저를 사용하여 웹 앱에 액세스할 수 있습니다.

{% endDetailsSummary%}

사용자는 웹 앱을 설치하기 전에 선택한 모든 브라우저를 사용하여 웹 앱에 액세스할 수 있습니다.

#### 이유

프로그레시브 웹 앱은 먼저 웹 앱이며, 이는 브라우저 중 하나에서가 아니라 여러 브라우저에서 작동해야 함을 의미합니다.

[탄력적인 웹 디자인](https://resilientwebdesign.com/)에서 Jeremy Keith이 한 말에 따르면 이를 수행하는 효과적인 방법은 핵심 기능을 식별하고 가능한 가장 간단한 기술을 사용하여 해당 기능을 사용할 수 있도록 한 다음 가능한 경우 경험을 향상시키는 것입니다. 대부분의 경우 이는 핵심 기능을 만들기 위해 HTML로 시작하고 CSS 및 JavaScript로 사용자 경험을 향상하여 보다 매력적인 경험을 만드는 것을 의미합니다.

양식 제출의 예를 보겠습니다. 이를 구현하는 가장 간단한 방법은 `POST` 요청을 제출하는 HTML 양식입니다. 이를 빌드한 후 JavaScript로 경험을 향상하여 양식 유효성 검사를 수행하고 AJAX를 통해 양식을 제출하여 이를 지원할 수 있는 사용자의 경험을 개선할 수 있습니다.

사용자가 다양한 장치와 브라우저에서 귀하의 사이트를 경험하게 될 것임을 고려하십시오. 스펙트럼의 상단을 단순히 타겟팅할 수는 없습니다. 기능 감지를 사용하면 현재 존재하지 않을 수 있는 브라우저 및 장치를 사용하는 사용자를 포함하여 가장 광범위한 잠재 사용자에게 유용한 경험을 제공할 수 있습니다.

#### 방법

Jeremy Keith의 [탄력적인 웹 디자인](https://resilientwebdesign.com/)은 이 크로스 브라우저, 진보적 방법론에서 웹 디자인에 대해 생각하는 방법을 설명하는 훌륭한 리소스입니다.

#### 추가 읽기

- A List Apart의 [점진적 개선의 이해](https://alistapart.com/article/understandingprogressiveenhancement/)는 이 주제에 대한 좋은 입문서입니다.
- Smashing Magazine의 [점진적 개선: 그것이 무엇이며 어떻게 사용합니까?](https://www.smashingmagazine.com/2009/04/progressive-enhancement-what-it-is-and-how-to-use-it/) 실용적인 소개와 고급 주제에 대한 링크를 제공합니다.
- MDN에는 기능을 직접 쿼리하여 기능을 감지하는 방법에 대해 설명하는 [기능 감지 구현](https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing/Feature_detection)이라는 기사가 있습니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

모든 화면 크기에 대응

사용자는 모든 화면 크기에서 PWA를 사용할 수 있으며 모든 콘텐츠는 모든 뷰포트 크기에서 사용할 수 있습니다.

{% endDetailsSummary %}

사용자는 모든 화면 크기에서 PWA를 사용할 수 있으며 모든 콘텐츠는 모든 뷰포트 크기에서 사용할 수 있습니다.

#### 이유

장치는 다양한 크기로 제공되며 사용자는 동일한 장치에서도 다양한 크기로 응용 프로그램을 사용할 수 있습니다. 따라서 콘텐츠가 표시 영역 내에 들어갈 뿐만 아니라 사이트의 모든 기능과 콘텐츠를 표시 영역 크기에 관계없이 사용할 수 있도록 하는 것이 중요합니다.

사용자가 완료하려는 작업과 액세스하려는 콘텐츠는 뷰포트 크기에 따라 변경되지 않습니다. 콘텐츠는 다양한 뷰포트 크기로 재배열될 수 있으며 모든 것이 어떤 식으로든 있어야 합니다. 사실, Luke Wroblewski가 그의 책 Mobile First에서 말했듯이, 크게 시작한 다음 축소하는 것이 아니라 작게 시작하여 확장하는 방식이 실제로 사이트 디자인을 개선할 수 있습니다.

> 모바일 장치를 사용하려면 소프트웨어 개발 팀이 애플리케이션에서 가장 중요한 데이터와 작업에만 집중해야 합니다. 320 x 480 픽셀 화면에는 불필요한 불필요한 요소를 위한 공간이 없습니다. 우선순위를 두어야 합니다.

#### 방법

[Ethan Marcotte의 글](https://alistapart.com/article/responsive-web-design/), 이와 관련된 [중요한 개념 모음](https://snugug.com/musings/principles-responsive-web-design/), 다양한 책 및 대화를 포함하여 반응형 디자인에 대한 많은 리소스가 있습니다. 이 논의를 반응형 디자인의 콘텐츠 측면으로 좁히기 위해 [콘텐츠 우선 디자인](https://uxdesign.cc/why-you-should-design-the-content-first-for-better-experiences-374f4ba1fe3c)과 [콘텐츠 출력형 반응형 레이아웃](https://alistapart.com/article/content-out-layout/)에 대해 알아볼 수 있습니다. 마지막으로 모바일에 중점을 두고 는 강의이지만 [Josh Clark의 모바일과 관련된 7가지 치명적인 미신](https://www.forbes.com/sites/anthonykosner/2012/05/03/seven-deadly-mobile-myths-josh-clark-debunks-the-desktop-paradigm-and-more/#21ecac977bca)은 모바일과 마찬가지로 반응형 사이트의 소규모 보기와 관련성이 있습니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

맞춤형 오프라인 페이지 제공

사용자가 오프라인일 때 PWA에 유지하면 기본 브라우저 오프라인 페이지로 돌아가는 것보다 더 원활한 환경을 제공합니다.

{% endDetailsSummary %}

사용자가 오프라인일 때 PWA에 유지하면 기본 브라우저 오프라인 페이지로 돌아가는 것보다 더 원활한 환경을 제공합니다.

#### 이유

사용자는 설치된 앱이 연결 상태에 관계없이 작동하기를 기대합니다. 플랫폼전용 앱은 오프라인일 때 빈 페이지를 표시하지 않으며 프로그레시브 웹 앱은 브라우저 기본 오프라인 페이지를 표시하지 않아야 합니다. 사용자가 캐시되지 않은 URL로 이동할 때와 사용자가 연결이 필요한 기능을 사용하려고 할 때 사용자 지정된 오프라인 경험을 제공하면 웹 경험이 실행 중인 장치의 일부인 것처럼 느낄 수 있습니다.

#### 방법

서비스 워커의 `install` 이벤트 중에 나중에 사용할 수 있도록 사용자 지정 오프라인 페이지를 미리 캐시할 수 있습니다. 사용자가 오프라인 상태가 되면 미리 캐시된 사용자 지정 오프라인 페이지로 응답할 수 있습니다. 맞춤형 [오프라인 페이지 샘플](https://googlechrome.github.io/samples/service-worker/custom-offline-page/)을 따라 실제 사례를 보고 직접 구현하는 방법을 배울 수 있습니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

설치 가능

기기에 앱을 설치하거나 추가하는 사용자는 해당 앱에 더 많이 참여하는 경향이 있습니다.

{% endDetailsSummary %}

기기에 앱을 설치하거나 추가하는 사용자는 해당 앱에 더 많이 참여하는 경향이 있습니다.

#### 이유

프로그레시브 웹 앱을 설치하면 설치된 다른 모든 앱처럼 보이고 느끼고 작동할 수 있습니다. 사용자가 다른 앱을 실행하는 동일한 위치에서 실행됩니다. 브라우저와 별도로 자체 앱 창에서 실행되며 다른 앱과 마찬가지로 작업 목록에 나타납니다.

사용자가 PWA를 설치하기를 원하는 이유는 무엇입니까? 사용자가 앱 스토어에서 앱을 설치하기를 원하는 것과 같은 이유입니다. 앱을 설치하는 사용자는 가장 참여도가 높은 잠재고객이며 일반 방문자보다 참여 측정항목이 더 우수하며 종종 휴대기기의 앱 사용자와 동등합니다. 이러한 측정항목에는 더 많은 반복 방문, 더 긴 시간 동안 사이트 및 더 높은 전환율이 포함됩니다.

#### 방법

[설치 가능 가이드](/customize-install/)를 따라 PWA를 설치 가능하게 만드는 방법, 설치 가능 여부를 테스트하는 방법, 직접 수행하는 방법을 배울 수 있습니다.

{% endDetails %}

## 최적의 프로그레시브 웹 앱 체크리스트 {: #optimal }

동급 최고의 앱처럼 느껴지는 진정으로 훌륭한 프로그레시브 웹 앱을 만들려면 핵심 체크리스트 그 이상이 필요합니다. 최적의 프로그레시브 웹 앱 체크리스트는 웹을 강력하게 만드는 요소를 활용하면서 PWA가 실행 중인 장치의 일부인 것처럼 느끼게 하는 것입니다.

{% Details %} {% DetailsSummary 'h3' %}

오프라인 경험 제공

연결이 엄격하게 필요하지 않은 경우 앱은 온라인과 동일하게 오프라인에서 작동합니다.

{% endDetailsSummary %}

연결이 엄격하게 필요하지 않은 경우 앱은 온라인과 동일하게 오프라인에서 작동합니다.

#### 이유

사용자 지정 오프라인 페이지를 제공하는 것 외에도 사용자는 PWA를 오프라인에서 사용할 수 있기를 기대합니다. 예를 들어 여행 및 항공사 앱에는 오프라인일 때 쉽게 사용할 수 있는 여행 세부정보와 탑승권이 있어야 합니다. 음악, 비디오 및 팟캐스팅 앱은 오프라인 재생을 허용해야 합니다. 소셜 및 뉴스 앱은 사용자가 오프라인일 때 읽을 수 있도록 최근 콘텐츠를 캐시해야 합니다. 사용자는 또한 오프라인 상태에서도 인증 상태를 유지하기를 기대하므로 오프라인 인증을 위해 설계하십시오. 오프라인 PWA는 사용자에게 진정한 앱과 같은 경험을 제공합니다.

#### 방법

사용자가 오프라인에서 작동할 것으로 기대하는 기능을 결정한 후에는 콘텐츠를 사용할 수 있고 오프라인 컨텍스트에 적용할 수 있도록 해야 합니다. 또한 브라우저 내 NoSQL 스토리지 시스템인 [IndexedDB](https://developers.google.com/web/ilt/pwa/working-with-indexeddb)를 사용하여 데이터를 저장 및 검색하고 사용자가 오프라인 상태에서 작업을 수행하고 사용자가 다시 안정적인 연결을 가질 때까지 서버 통신을 연기할 수 있도록 [백그라운드 동기화](https://developers.google.com/web/updates/2015/12/background-sync)를 사용할 수 있습니다. 서비스 워커를 사용하여 오프라인 사용을 위한 이미지, 비디오 파일 및 오디오 파일과 같은 다른 종류의 콘텐츠를 저장하고 사용자 인증을 유지하기 위해 [안전하고 수명이 긴 세션](https://developers.google.com/web/updates/2016/06/2-cookie-handoff)을 구현하는 데 사용할 수도 있습니다. 사용자 경험 관점에서 로드하는 동안 사용자에게 속도와 콘텐츠에 대한 인식을 제공한 다음 필요에 따라 캐시된 콘텐츠 또는 오프라인 표시기로 대체할 수 있는 [스켈레톤 화면](https://uxdesign.cc/what-you-should-know-about-skeleton-screens-a820c45a571a)을 사용할 수 있습니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

완전히 접근 가능

모든 사용자 상호 작용은 [WCAG 2.0](https://www.w3.org/TR/WCAG20/) 접근성 요구 사항을 통과합니다.

{% endDetailsSummary %}

모든 사용자 상호 작용은 [WCAG 2.0](https://www.w3.org/TR/WCAG20/) 접근성 요구 사항을 통과합니다.

#### 이유

대부분의 사람들은 인생의 어느 시점에서 [WCAG 2.0](https://www.w3.org/TR/WCAG20/) 접근성 요구 사항에서 다루는 방식으로 PWA를 활용하기를 원하게 될 것입니다. PWA와 상호 작용하고 이해하는 인간의 능력은 스펙트럼 형태로 존재하며 요구사항은 일시적이거나 영구적일 수 있습니다. PWA에 액세스할 수 있게 하면 모든 사람이 사용할 수 있습니다.

#### 방법

W3C의 [웹 접근성 개론](https://www.w3.org/WAI/fundamentals/accessibility-intro/)은 시작하기에 좋은 곳입니다. 접근성 테스트의 대부분은 수동으로 수행해야 합니다. Lighthouse의 [접근성](https://github.com/dequelabs/axe-core) 감사, [axe](https://accessibilityinsights.io/) 및 [Accessibility Insights](/lighthouse-accessibility/)와 같은 도구를 사용하면 일부 접근성 테스트를 자동화할 수 있습니다.  `a`나 `button`과 같은 요소를 스스로 재창조하는 대신 의미적으로 올바른 요소를 사용하는 것도 중요합니다. 이렇게 하면 더 고급 기능을 구축해야 할 때 접근성 기대치를 충족할 수 있습니다(예: 화살표와 탭을 사용해야 하는 경우). [A11Y 영양 카드](https://accessibilityinsights.io/)에는 몇 가지 일반적인 구성 요소에 대한 훌륭한 조언이 있습니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

검색을 통해 찾을 수 있음

귀하의 PWA는 [검색을 통해 쉽게 찾을 수 있습니다](/discoverable/).

{% endDetailsSummary %}

귀하의 PWA는 [검색을 통해 쉽게 찾을 수 있습니다](/discoverable/).

#### 이유

웹의 가장 큰 장점 중 하나는 검색을 통해 사이트와 앱을 찾을 수 있다는 것입니다. 실제로 모든 웹사이트 트래픽의 [절반 이상](https://www.brightedge.com/resources/research-reports/channel_share)이 자연 검색에서 발생합니다. 콘텐츠에 대한 표준 URL이 존재하고 검색 엔진이 사이트를 색인화할 수 있는지 확인하는 것은 사용자가 PWA를 찾을 수 있도록 하는 데 중요합니다. 이것은 클라이언트 사이드 렌더링을 채택할 때 특히 그렇습니다.

#### 방법

각 URL에 고유하고 설명적인 제목과 메타 설명이 있는지 확인하는 것부터 시작하세요. 그런 다음 [Google Search Console](https://search.google.com/search-console/about) 및 Lighthouse의 [검색 엔진 최적화 감사](/lighthouse-seo/)를 사용하여 PWA의 검색 가능성 문제를 디버깅하고 수정할 수 있습니다. 또한 [Bing](https://www.bing.com/toolbox/webmaster) 또는 [Yandex](https://webmaster.yandex.com/welcome/)의 웹마스터 도구를 사용하고 PWA에서 [Schema.org](https://goo.gle/search-gallery)의 스키마를 통해 [구조화된 데이터](https://schema.org/)를 포함하는 것을 고려할 수 있습니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

모든 입력 유형에서 작동

PWA는 마우스, 키보드, 스타일러스 또는 터치로 동일하게 사용할 수 있습니다.

{% endDetailsSummary %}

PWA는 마우스, 키보드, 스타일러스 또는 터치로 동일하게 사용할 수 있습니다.

#### 이유

장치는 다양한 입력 방법을 제공하며 사용자는 응용 프로그램을 사용하는 동안 원활하게 전환할 수 있어야 합니다. 마찬가지로 중요한 것은 입력 방법이 화면 크기에 의존해서는 안 된다는 것입니다. 즉, 큰 표시 영역은 터치를 지원해야 하고 작은 표시 영역은 키보드와 마우스를 지원해야 합니다. 최선을 다해 애플리케이션과 모든 기능이 사용자가 선택할 수 있는 모든 입력 방법을 지원하는지 확인하십시오. 적절한 경우 입력별 컨트롤(예: 끌어서 새로 고침)을 허용하도록 경험도 향상해야 합니다.

#### 방법

[포인터 이벤트 API](https://developers.google.com/web/updates/2016/10/pointer-events)는 다양한 입력 옵션 작업을 위한 통합 인터페이스를 제공하며 특히 스타일러스 지원을 추가하는 데 유용합니다. 터치와 키보드를 모두 지원하려면 올바른 의미 요소(앵커, 버튼, 양식 컨트롤 등)를 사용하고 있는지 확인하고 이러한 요소를 의미 없는 HTML(접근성에 좋음)로 다시 작성하지 마세요. 호버링 시 활성화되는 상호작용을 포함할 때 클릭 또는 탭 시에도 활성화될 수 있는지 확인하십시오.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

권한 요청에 대한 컨텍스트 제공

강력한 API 사용 권한을 요청할 때 컨텍스트를 제공하고 API가 필요할 때만 요청하십시오.

{% endDetailsSummary %}

강력한 API 사용 권한을 요청할 때 컨텍스트를 제공하고 API가 필요할 때만 요청하십시오.

#### 이유

알림, 지리적 위치 및 자격 증명과 같은 권한 프롬프트를 트리거하는 API는 옵트인이 필요한 강력한 기능과 관련되는 경향이 있기 때문에 의도적으로 사용자에게 방해가 되도록 설계되었습니다. 페이지 로드와 같이 추가 컨텍스트 없이 이러한 프롬프트를 트리거하면 사용자가 해당 권한을 수락할 가능성이 줄어들고 나중에 이를 불신할 가능성이 높아집니다. 대신 해당 권한이 필요한 이유에 대해 사용자에게 상황에 맞는 근거를 제공한 후에만 해당 프롬프트를 트리거하십시오.

#### 방법

[권한 UX](https://developers.google.com/web/fundamentals/push-notifications/permission-ux) 기사와 UX Planet의 [사용자에게 권한을 요청하는 올바른 방법](https://uxplanet.org/mobile-ux-design-the-right-ways-to-ask-users-for-permissions-6cdd9ab25c27)은 모바일에 초점을 맞추면서 모든 PWA에 적용되는 권한 프롬프트를 디자인하는 방법을 이해하는 데 좋은 리소스입니다.

{% endDetails %}

{% Details %} {% DetailsSummary 'h3' %}

건전한 코드를 위한 모범 사례를 따릅니다

코드베이스를 건전하게 유지하면 목표를 달성하고 새로운 기능을 제공하기가 더 쉬워집니다.

{% endDetailsSummary %}

코드베이스를 건전하게 유지하면 목표를 달성하고 새로운 기능을 제공하기가 더 쉬워집니다.

#### 이유

현대적인 웹 애플리케이션을 구축하는 데 필요한 것이 많습니다. 애플리케이션을 최신 상태로 유지하고 코드베이스를 건전하게 유지하면 이 체크리스트에 나와 있는 다른 목표를 충족하는 새로운 기능을 더 쉽게 제공할 수 있습니다.

#### 방법

건전한 코드베이스를 보장하기 위한 우선순위가 높은 여러 검사가 있습니다. 알려진 취약점이 있는 라이브러리 사용 방지, 사용되지 않는 API를 사용하지 않는지 확인, 코드베이스에서 웹 안티 패턴 제거(예: `document.write()` 또는 논패시브 스크롤 이벤트 리스너), 분석 또는 기타 타사 라이브러리가 로드되지 않는 경우 PWA가 중단되지 않도록 방어적으로 코딩합니다. 여러 브라우저 및 릴리스 채널에서 린팅과 같은 정적 코드 분석과 자동화된 테스트를 요구하는 것을 고려하십시오. 이러한 기술은 오류가 프로덕션에 적용되기 전에 오류를 포착하는 데 도움이 될 수 있습니다.

{% endDetails %}
