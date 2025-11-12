Ohouse ai key flows 

*near-term integration with Ohouse KR*
Start with your room, end with your room - different from current discovery experience - browing inspiration that's not yours - guestimation whether it's going to fit in your room or not.

**Onboarding**
\“So, currently we're just asking what people wanted, but instead of it, we're just taking a visual. What space are you looking to change? And give me the thought of it, and let us know what other products that you wanted to think about it. And your entire experience is starting from your space.”
사용자의 사진으로 부터 시작하는 플로우 
- 사진을 업로드하면 사진 분석 
- 분석된 내용이 무엇이 있는지 보여주고 
- 분석된 내용 기반으로 Shopping home이 구축됨 
- 여기서 여러 공간의 사진을 올리면?
ㄴ 각 공간별로 필터링 하면서 공간에 필요한 상품들 추천들을 볼 수 있음 

**PDP** 
“So, from the PDP, what we wanted to give to the people is that people see the products in the staging way, and sometimes there are review photos that are placed in the real settings, but that's not their home. So, we're offering people to view the product in their home, render on the request, or we can try to pre-render some of the stuff there you might be interested in.”
“And so you don't have to necessarily see the products from the other view. So this is a pretty much like, oh, everything is designed about your home.
- Hero carousel of product photos 
- scrolling thru - there is your room photo & you can see how it would look in your room (or pre-rendering if possible) - or the process kicks in when users swiping thru product photo - which will take 10-15s for generations 
- And users can see multiple variations for layout, different position 
- and can also discover other similar products rendered in the photo viewers 
- And this photo can be transformed to Room planner where users don't have to wait but play with the furniture easily 
- and also how it looks in 4k rendering 
- and also can view it in AR for sensing the real scale 


**Content consumption (becomes part of creation)**
Basically whenver you find inspiring photo - you can see whether it would fit in your room
- If you like a content from other users, you can transfer the style to your room and how it fits 
- or select a furniture of what you like and place to your room 
- Same for finding interior contractor - you can style transfer 


**AI-consultation & Community**
- 물론 질문 이전에 스스로 인테리어에 대한 해답을 찾을 수 있긴함. (근데 이런건 chatgpt가 더 잘할 거고)- 우리 입장에서는 서비스로 연결해주는게 이득일 거임. 이런거 사면되 이런 거 설치하면 돼 혹은 이런 콘텐츠 보면 돼.
- 여전히 사진 한장 띡 던지고 물어보는 사람들에게 사람들도 글로 답변하는게 아니라 실제 제안이 시각화되서 볼 수 있게 구조적으로 던져줌. (단계별로 설득해야하니까)


그리고 여기까지가 near-term인데 이걸 통해서 우리는
- LLM + 시각화 기술에 대한 고도화 (system prompt)
- Integrating with existing SKU at Ohouse 
- Room planner를 위해 Image to 3D (PDP의 사진에서 3D 모델링 추출 자동화)-이건 이미 자동화됨 
- Image to RP (Room planner)
- Building model for better recommendation (To be built)
- With existing Room planner - 공간과 가구들의 상관관계에 대한 modeling 
- 사진으로부터도 추출가능해서 독보적인 RAG모델을 만드는 걸로 출발


다만 국내에 integration만으로는 사실상 원래 한계인 기존 시장의 cap을 더 키우는 건 어려움. 아마 저기에 있는 것들은 구매 전환율 향상에 크게 도움이 되나 그것만으로는 회사가 2x할 수 있는 규모는 아님 - 근본적으로 외부-> 내부 트래픽이 들어오는 구조는 아니기 때문에 

그래서 넘어가는게 

**Standalone app - Ohouse AI **
위에 쌓아놓은 기술들로 우리가 하려는게 사실 이거임 - 왜냐고? 국내는 판매를 하지 않으면 근본적으로 수익이 안됨. 물론 수익 구조 개선, 그리고 새로운 user segment타겟팅, 인테리어 시공 사업으로 공격적 확장을 하고 있지만 이또한 국내에 한정. 
기본적으로 오늘의집이 가지고 있는 Content(consumption) -> Commerce (Conversion)의 비지니스는 글로벌 확장성이 없음 - 물론 판매 시도중이지만 매우 천천히 크는 중 경쟁도 많고 

가장 근본적인 변화는 Consumption -> Conversion에서 (남의 것을 보고 받는 영감에서) Creation -> Conversion (나의 것에서 실행을 위한 단초를 얻는) 모델로 가는게 핵심임. 이미 Room planner에서 이런 시그널들을 확인해왔었음. 스케일의 문제도 있는데 Photo generation combinated with RP가 이런 부분들을 해결해줄 거임. 

그래서 Standalone앱에서는 어떤 경험을 제공할 것인지를 좀 더 정리해야하는데 
- 여기서 가려고 하는 건 좀 더 AI native agentic한 경험을 주는게 목표 
- 이게 무슨 말인가 하면 유저가 테스크를 주면 지금 claude code나 cursor처럼 중간 과정을 보여주면서 동의를 받긴 하지만 - 기본적으로는 마치 실제 인테리어 디자이너에게 일을 맡기는 것 같이 고객은 "정보와 테스크를 제공하고" - 서비스 제공자는 "결과물을 제시하고" 이를 기반으로 고객은 피드백을 주고 평가해서 결론에 최단 기간에 도달하는 그런 방식으로 가야한다고 생각함. 
- 이걸 디자인하려면 빡세긴 할 것 같은데 ----결국 챗 경험일 것 같고 (만들 거 많겠네)
- 여기에 포함되어야 하는 건 -우리가 리서치를 통해서 얻은 것 중에 하나는 사람들은 validation을 받고 싶어하기 때문에 결과물에 대한 "다른 사람의 평가"를 받을 수 있는 voting?할 수 있는 자리도 마련되어있음. 
- 그리고 시작이 망설여지는 사람들을 위해서 다양한 공간의 inspiration을 받을 수 있는 Explore feed도 있고 - 이것 역시 Creation으로 다시 돌아가게 하는 거 
- 그리고 마이 페이지 같은 경우는 내 결과물을 모아두는 자리이긴 하지. 

그리고 이건 구독모델로 돌아갈 거야. 미국 시장을 노릴 거고 - 상품 같은 경우는 꼭 우리 상품이 아니더라도 affiliate이나 자체 크롤링을 통할 예정 - (그리고 우리도 Ohouse US에 이미 상품 DB확보해놓은 것도 있음)


이렇게 얻어진 트래픽과 기술이 과연 뭘 의미하는가를 생가갛면 결국은
누구보다 쉽게 디지털 트윈을 만들어내고 재현하며 그 안의 공간들을 다양하게 꾸며볼 수 있게 하는게 우리의 목표고 - 이 기술들과 engagement를 가지고 Property management의 방 리스팅 사진을 생성해주거나? (스토리상 좀 길어보일 수도 있는데)결국 집을 구하려거나 사려고 하는 사람들이 실제 최종 후보군에서 지금 내가 사는집에 있는 가구들을 가지고 꾸며볼 수 있도록 있게 해서 집을 결정하는데 더 확정적으로 도움을 줄 수 있도록 하고 - 계정 정보 연동을 통해서 집을 구매/렌트한 이후에 다시 Standalone앱으로 올 수 있게 - 이 관점에서 우리는 prop tech으로서 경쟁력있는 가격을 확보할 수 있고 - Enterprise Sass solution - 이유는 우리가 타겟팅하는 이사/시공 유저들이 모두 오기 때문에 - 자연스럽게 Ohouse AI로 경험을 transition해서 지속적인 수익 모델은 여기서 나오고 유저들에게는 전체적으로 편의성을 제공하는 경험을 주겠다.