## 아바타 과제(박윤선)

### HTML

```html
<main class="main">
  <div class="group1" aria-label="여성 프로필 그룹">
    <img class="img" src="../images/faces/face1.jpg" alt="여자1" />
    <img class="img" src="../images/faces/face2.jpg" alt="여자2" />
    <img class="img" src="../images/faces/face3.jpg" alt="여자3" />
    <img class="img" src="../images/faces/face4.jpg" alt="여자4" />
    <div class="woman-btn" aria-label="여성 프로필 상태 버튼">
      <div class="off-btn"></div>
      <div class="on-btn"></div>
      <div class="off-btn"></div>
      <div class="on-btn"></div>
    </div>
  </div>
</main>
```

이미지와 off, online 버튼을 하나의 그룹으로 묶어 여성 프로필은 group1으로 class를 부여했다.<br/>
같은 방법으로 남성 프로필도 group2로 class를 부여했다. <br/>
이는 flex 지원 환경에서 남자 행과 여자 행을 바꾸기 위해서다.

### CSS

```css
.main {
  width: 340px;
  height: 166px;
  margin: 230px 530px;
}
```

main 클래스에서는 이미지와 버튼이 들어갈 사이즈의 박스를 만들기 위해 적당한 숫자로 width와 height값을 부여한 뒤 화면 가운데에 있는 것처럼 보이기 위해 박스에 margin값을 적당히 부여하였다.

```css
.img {
  width: 64px;
  height: 64px;
  border-radius: 70%;
  float: left;
  margin: 10px;
}
```

이미지의 사이즈를 width, height에 64px로 부여하였고 원 모양으로 만들기 위해 border-radius 값을 크게 주었다.<br/>
float: left하여 왼쪽으로 정렬시켰고 간격은 20px로 만들기 위해 각 이미지마다 margin을 10px로 주었다.

```css
.woman-btn,
.man-btn {
  width: 340px;
  height: 83px;
  position: absolute;
}

.man-btn {
  margin-top: 83px;
}
```

위치한 버튼을 묶어서 여성 프로필 버튼과 남성 프로필 버튼으로 나누기 위해 content-box로 box-sizing.<br/>
남성 프로필 버튼을 더 아래로 위치시키기 위해 magin값을 주었다.

```css
.off-btn {
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background-color: #dbdbdb;
  border: 1px solid #eaeaea;
  float: left;
  margin: 55px 13px 0px 55px;
}

.on-btn {
  width: 15px;
  height: 15px;
  border-radius: 50%;
  background-color: #4cfe88;
  border: 1px solid #eaeaea;
  float: left;
  margin: 55px 13px 0px 55px;
}
```

버튼 사이즈는 적당히 가로, 세로 15px로 하고 모서리 각 50%로 원으로 만들었다.<br/>
마진 값을 위, 오른쪽, 왼쪽에 주어 원하는 위치에 위치시키고 float를 왼쪽으로 정렬시켰다.

```css
@supports (display: flex) {
  .main {
    display: flex;
    flex-flow: column nowrap;
  }

  .group2 {
    order: -1;
  }

  .man-btn {
    margin-top: 0px;
  }
}
```

flex를 지원하는 환경에서는 여성 프로필에 해당하는 group1과 남성 프로필에 해당하는 group2가 열방향으로 바뀔 수 있도록 flex-direction은 column,wrap은 적용되지 않도록 nowrap 그리고 group2의 순서를 -1로 지정해 가장 먼저 오도록 했고 이 때 남성 프로필 버튼 그룹의 위 margin을 0으로 변경하여 위치를 조정했다.
