# yoon-play🎵
## 배포 링크 
> https://yoon-play.netlify.app/

## 기술 스택
> React, TypeScript, Recoil, scss

> Youtube API, Figma

### 해당순서를 통해 api key를 발급 받을 수 있습니다.  :)
1) 링크 접속
https://console.cloud.google.com/apis/dashboard
2) 새 프로젝트 생성
3) API 및 서비스 사용설정에서 Youtube Data API v3 검색 후 사용 클릭
4) 사용자 인증 정보 만들기에서 정보 입력 후 API Key 발급 받기


<br/>

## 1. 기획 ✏
해당 프로젝트의 기획은 이렇습니다! <br/>
> "그날의 분위기와 기분에 따라 음악을 추천해주는 뮤직플레이어는 어디 없을까?"

위와 같은 생각을 하게되었고 나만의 감정 뮤직플레이를 만들어보고자 해당 프로젝트를 기획하였습니다.

메뉴는 **``무드 선택, 무드플레이, 마이플레이, 검색``** 이 있습니다.

### 1.1) 무드 선택
- 유저가 오늘 하루의 기분, 분위기 및 감정에 알맞는 카테고리를 선택할 수 있는 페이지 입니다.
- 두 가지 선택지를 모두 클릭했을 시에만 하단 MOOD PLAY버튼을 누르면 무드플레이 화면으로 넘어갑니다.
- 두 가지 선택지 중 하나라도 클릭하지 않았을 때는 안내 모달창이 나타납니다. 

#### 첫번째 카테고리 선택_메인 감정 🙂
- 먼저 상단의 카테고리를 선택합니다.
- 해당 카테고리는 현재 ``'차분한'``, ``'신나는'`` 두가지가 있으며 피드백을 받은 후 추가할 예정입니다.

#### 두번째 카테고리 선택_메인 감정에 맞는 상황 🙂
- 상단의 카테고리를 선택하면 그 키워드의 알맞는 두번째 카테고리가 나타납니다.
- ``차분한``을 클릭 시 ``잠잘 때``, ``집중할 때``, ``힘이 필요할 때``, ``편안한 분위기`` 의 카테고리가 나오며 더 많은 카테고리는 추후에 추가할 예정입니다.
- ``신나는``을 클릭 시 ``기분 좋을 때``, ``운동할 때``, ``힘이 필요할 때``의 카테고리가 나오며 더 많은 카테고리는 추후에 추가할 예정입니다.

### 1.2) 무드 플레이
- 유저가 선택한 기분, 분위기에 어울리는 장르들을 선택할 수 있는 페이지입니다.
- ``차분한``에 어울리는 장르 리스트는 ``어쿠스틱``, ``지브리``, ``재즈``, ``뉴에이지``, ``로파이``, ``발라드``, ``팝``이 있으며 추후에 장르 리스트를 추가할 예정입니다.
- ``신나는``에 어울리는 장르 리스트는 ``댄스``, ``R&B``, ``팝``, ``어쿠스틱``, ``힙합``이 있으며 추후에 장르 리스트를 추가할 예정입니다.
- 유저가 원하는 장르를 클릭하면 하단에 뮤직 리스트가 나타납니다.
- 뮤직리스트 중 듣고싶은 노래를 클릭하면 음악이 시작되며 하단에 음악 정보가 나타납니다.
- 하단 뮤직 플레이어에 북마크 아이콘이 있으며 해당 아이콘을 클릭 시 나만의 플레이 리스트에 추가할 수도, 추가 되어있는 리스트를 삭제할 수도 있는 창이 나타납니다.

### 1.3) 마이플레이
- 나만의 플레이리스트의 정보들이 나열되어 나타납니다.
- 해당 플레이 리스트는 ``localStorage``에 저장이 되어있습니다.
- 플레이 리스트 중 듣고싶은 노래를 클릭하면 음악이 시작되며 하단에 음악 정보가 나타납니다.
- 하단 뮤직 플레이어에 북마크 아이콘이 있으며 해당 아이콘을 클릭 시 플레이 리스트에서 삭제할 수 있는 창이 나타납니다.

### 1.4) 검색
- 제공되는 카테고리에서 유저가 원하는 항목이 없을 경우 검색할 수 있는 페이지입니다.
- 원하는 검색 키워드를 입력한 뒤 enter 또는 우측 검색버튼을 누르면 해당 키워드의 플레이리스트가 검색됩니다.
- 검색결과는 하단에 나타나며 듣고싶은 노래를 클릭하면 음악ㅇ 시작되며 하단에 음악정보가 나타납니다.
- 하단 뮤직 플레이어에 북마크 아이콘이 있으며 해당 아이콘을 클릭 시 나만의 플레이 리스트에 추가할 수도, 추가 되어있는 리스트를 삭제할 수도 있는 창이 나타납니다.

## 2. UI 🎨
- Navigation은 좌측 사이드바로 나타내었으며 메뉴는 **``무드 선택, 무드플레이, 마이플레이, 검색``** 이 있습니다.
- **``Yoon-Play``** 의 메인 색상은 그린계열로 나타내었습니다.
- 하단 뮤직 플레이어는 블러처리를 하여 UI가 깔끔해보이고 음악정보에 더 집중할 수 있도록 하였습니다.
- 하단 뮤직 플레이어에 실행되고 있는 뮤직의 이미지를 border-radius와 before태그를 이용하여 CD의 이미지를 연상시킬 수 있도록 하였습니다.

## 3. 구현 
- 데이터의 상태관리는 ``Recoil`` 을 이용하였습니다.
- 선택한 분위기,기분의 카테고리와 장르 키워드를 플레이리스트 키워드와 함께 API를 호출하도록 하였습니다.
- Axios를 이용하여 API 요청이 성공적으로 이루어졌을 경우 검색결과가 나타나며 듣고싶은 혹은 원하는 뮤직을 클릭하여 즐겨찾기를 할 수 있으며 해당 데이터는 localStorage에 저장하도록 하였습니다.
- recoil-persist를 이용하여 새로고침하여도 데이터가 localStorage에 저장되도록 하였습니다.
- localStorage에 저장되어있는 뮤직 데이터는 마이 플레이에 불러와 map()을 이용하여 나타내었습니다.
- 마이 플레이에 저장되어있는 뮤직은 무드플레이에서 구분할 수 있도록 하트 아이콘으로 나타내었고, 데이터가 있다면 색이 채워진 하트가, 데이터가 없다면 책이 채워져있지 않은 하트가 나타납니다.

## 4. 결과물
### 4-1) 무드 선택
![1](https://user-images.githubusercontent.com/65527334/173240724-e6d5dad6-d096-49a0-aa2a-87991420b909.gif)

### 4-2) 무드플레이
![2](https://user-images.githubusercontent.com/65527334/173241085-21910a5e-e279-40e5-8044-a50a49d4ceb6.gif)

### 4-3) 마이플레이
![3](https://user-images.githubusercontent.com/65527334/173241170-1860215b-20ce-477b-902d-a176d14e39a0.gif)

### 4-4) 검색
![4](https://user-images.githubusercontent.com/65527334/173241439-c923fe80-592d-4bbf-93bc-b45acd5fe115.gif)


## 5. 마무리하며 느낀점
Yoon-Play를 구현하면서 디자인을 중요하게 생각하였고 수많은 레퍼런스를 하였고 원하는 화면이 나올 때까지 피그마로 그림을 그려가며 완성을 했습니다. 기획부터 디자인 그리고 기능 구현까지 모든것을 혼자 하다보니 처음 시작하는 게 어려웠던 것 같습니다. 하지만 하나씩 기획을 하며 정하고 난 뒤 조금씩 속도를 붙일 수 있었고 2일동안 밤새워가며 완성한 프로젝트입니다. 좀 더 완벽하게 프로젝트를 완성하고 싶었지 그렇지 못한 것에 아쉬움이 남는 것 같습니다. Youtube Api를 이용하여 하는 것이기때문에 하루 할당량을 다 사용하고 나면 ``403`` 에러가 나며 화면이 나타나지 않는데 이부분을 에러가 나면 문구를 나타내어 처리할 수 있을 것 같았지만 맘처럼 쉽게 되지않아 해당 기능은 구현을 하지 못하였습니다. 그리고 뮤직을 정지하고 재생하는 기능과 볼륨 조절은 가능하지만 이전이나 다음 뮤직 리스트로 나타내는 것도 구현이 되어있지 않아 아쉬움이 남습니다 추후에 추가적으로 보완을 해야겠다 라는 생각을 하게되었습니다.
아쉬움이 남기는 하지만 디자인이나 기획에 있어서 만족하는 프로젝트이며 React에 대해 더 깊게 알 수 있는 시간이었고 힘들었던 만큼 뿌듯함이 2-3배가 되는 것 같습니다!

해당 코스의 마지막 과제라는 것에 더욱 더 열심히 임하였고 마무리를 좋게할 수 있게 되어서 좋습니다! 한달동안 정말 많이 배웠고 프로젝트를 하며 React에 대해 잘 알 수 있게 됐던 시간이었습니다. 감사합니다.


