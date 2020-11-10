<template>
    <header id="header">
    <h1>headerdesu</h1>
    <nav id="header-nav">
      <ul>
        <router-link tag="li" id="home-nav" to="/" exact><a>ホーム</a></router-link>
        <router-link tag="li" id="game-nav" to="/search"><a>検索</a></router-link>
        <router-link tag="li" id="info-nav" to="/calender"><a>カレンダー</a></router-link>
        <router-link tag="li" id="gift-nav" to="/mypage"><a>マイページ</a></router-link>
      </ul>
    </nav>
  </header>
</template>

<script scoped>
  export default {
  }

</script>
