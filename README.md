## NextJS로 만들어진 중고마켓 홈페이지입니다.<br/>현재 Server관리 문제로 Deploy는 안되어있습니다.

<hr/>

## Server

Server의 경우 Docker를 이용하여 locahost:5432에서 동작시켰습니다.<br/>
prisma로 db가 구성되었으며 db의 상세 내용은 "prisma/schema.prisma"에서 확인부탁드립니다.

<hr/>

## Home Page

Home Page는 NavigationBar, Category, Product, Pagination, ProdcutUploadButton으로 구성되어있습니다.<br/>
![HomePage](https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/703c3074-1d27-404f-880c-9644395302bc)

<hr/>

## Pagination

Pagination의 경우 동적으로 제작되었으며 한 페이지에 최대 6개의 상품만 보여지게 설정되어있습니다.<br/>
만약 6개가 초과되는 경우 화살표 또는 숫자 Page를 Click하여 현재 보여진 상품정보 이후의 상품정보를 확인 할 수 있습니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/264c47e7-93dc-4492-a749-d2870e8b2a1b

<hr/>
## SignIn

SignIn(Login)은 SignIn Button을 Click 시 Login Page로 넘어가게되고 Login에 성공하면<br/> NavigationBar에 SignIn Button을 삭제하고, Chat과 SignOut Button을 추가된 Layout으로 보여지게됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/ac77309b-dbc4-4917-98b3-a032fcdd4b5b

<hr/>

## Register

Register(회원가입)의 경우 Login Page 하단에 Register Button을 Click하면 Register Page로 넘어가게되고<br/>
Email, Name, Password를 입력하고 Register Button을 Click 시 Server로 Auth 정보가 전송됩니다.<br/>
Auth 정보는 "next-auth"로 관리되며, "bcryptjs"로 Password 암호화를 진행하여 HashPassword를 Server로 전송하게됩니다.<br/>
Server로 모든 정보가 전송되면 Login Page로 이동시켜 Login이 가능하게됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/40b668ca-70fe-4b55-9f58-db32f2d6d7f5

<hr/>

## SignOut

SignOut(Logout)은 SignOut Button을 Click시 "next-auth"에서 지원해주는 signOut 함수를 이용하여 홈페이지에 있던 User 정보를 지워줍니다.<br/>
SignOut이 되게되면 SignIn과 반대로 NavigationBar에 Chat과 SignOut Button이 사라지고,<br/>
SignIn Button이 추가된 Layout으로 보여지게됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/30b0a54c-d3be-480f-a7dd-ebc64b6c63e8

<hr/>

## Detail Page

Detail Page(상품 상세정보)의 경우 Home Page에서 상품을 Click 시 Detail Page로 넘어가게되며<br/>
상품의 Title, 첨부한 사진, 글을 작성한 User 정보, 글을 작성한 시간, 상품의 Category, 상품의 Description,<br/>
Upload 시 지도에서 설정한 위치를 보여주는 Kakao Map, 채팅으로 이동시켜주는 버튼으로 구성되어있습니다. <br/>

![DetailPageImage](https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/7adb67f6-a20a-4b04-b633-03ba272effe4)

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/884279c8-ccbf-4170-a278-c651177aa919

<hr/>

## Product Upload

Home Page 우측 하단에 + Button을 Click하면 Upload Page로 접속됩니다.<br/>
사진 첨부가 되는 Section을 Click하게되면 Cloudinary Service를 이용하여 사진을 첨부하게됩니다.<br/>
추가로 Title, Description, Price 입력 후 Category 선택 후 KakaoMap을 Click하면 위치 정보가 위도 경도 기준으로 바뀌게되며,<br/>
내가 원하는 위치를 선택한 후 상품 생성하기 Button을 Click하면 입력한 정보가 Server로 전송됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/fc7e83bd-0ade-4b3b-a6b4-f4a0b4dee880

<hr/>

## Favorite

Favorite의 경우 상품 이미지 우측 상단에 있는 Heart Button으로 즐겨찾기에 추가 및 삭제를 할 수 있습니다.<br/>
즐겨찾기에 추가 및 삭제가 진행되면 Page 우측 상단에 Toast Popup을 띄어 안내를 해주었습니다.<br/>
HomePage 또는 DetailPage에 있는 Heart Button 모두 동작되됩니다.<br/>
그리고 Heart Button Click 시 Server로 정보가 전송되어 즐겨찾기가 계정별로 관리됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/2c35a0bd-f222-42ec-a3d3-9ea66b286282

<hr/>

## Category Filter

Category는 디지털기기, 생활가전, 가구/인테리어, 여성의류, 남성패션/잡화, 뷰티/미용, 스포츠/레저, 중고차로 이루어져있습니다.<br/>
Home Page에서 원하는 Category를 Click하게되면 Category별 Filter가 동작하게 되며,<br/>
상풍 생성할때 입력하였던 Category를 기준으로 Filtering하여 상품 정보를 보여주게됩니다.<br/>
Filtering된 정보가 없으면 "일치하는 항목이 없습니다."라는 문구를 출력하고,<br/>
모든 필터 제거 Button Click 시 Filter가 전부 제거되어 상품 정보를 보여주게됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/3c5791ec-751d-40e1-aeb0-848bec84dc15

<hr/>

## Chat

Chat의 경우 NavigationBar Chat Button 또는<br/>
상품 DetailPage 최하단 이 유저와 채팅하기 Button을 통해 Chat Page로 진입 할 수 있습니다.<br/>
SWR을 이용하여 Chat 기능을 구성하였고 실시간 Chating처럼 보여지게됩니다.<br/>
Chat Message를 입력하여 전송하면 Server에 Message 내용을 전송하게되고,<br/> Server가 받으면 SWR이 Trigger되어 화면에 나타나던 Chat 내용이 다시 Randering됩니다.<br/>
사진 첨부 기능도 추가하였으며, 해당 기능도 Product Upload와 동일하게 Cloudinary Service를 이용하여 대화를 구성하게됩니다.<br/>

https://github.com/Yuhyeon0516/nextjs-usedmarket-app/assets/120432007/bc22e2a5-4498-4495-aee3-84323b611dcf
