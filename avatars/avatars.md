## 박윤선 - 아바타 과제

과제 어떻게 만든건지 설명, 느낀점, 배운점 있으면 자유롭게 쓰면 됨
### HTML

```html
<main class="main">
      <div class="group1">
        <img class="img1 img" src="../images/faces/face1.jpg" alt="여자1" />
        <img class="img2 img" src="../images/faces/face2.jpg" alt="여자2" />
        <img class="img3 img" src="../images/faces/face3.jpg" alt="여자3" />
        <img class="img4 img" src="../images/faces/face4.jpg" alt="여자4" />
        <div class="woman-btn">
          <div class="off-btn1 off-btn"></div>
          <div class="on-btn1 on-btn"></div>
          <div class="off-btn2 off-btn"></div>
          <div class="on-btn2 on-btn"></div>
        </div>
      </div>
```


이미지와 off, online 버튼을 하나의 그룹으로 묶어 여성 프로필은 group1으로 class를 부여했다.
같은 방법으로 남성 프로필도 group2로 class를 부여했다. 이는 flex 지원 환경에서 남자 행과 여자 행을 바꾸기 위해서다.

```css
.main {
  width: 500px;
  height: 166px;
  margin: 230px 530px;
  display: flow-root;
}
```

