<template>
  <f7-page name="home">

    <f7-navbar>
      <f7-nav-left>
        <f7-link icon-ios="f7:menu" icon-aurora="f7:menu" icon-md="material:menu" panel-open="left"></f7-link>
      </f7-nav-left>
      <f7-nav-title>My Chat</f7-nav-title>
      <f7-nav-right>
        <f7-link icon-ios="f7:menu" icon-aurora="f7:menu" icon-md="material:menu" panel-open="right"></f7-link>
      </f7-nav-right>
    </f7-navbar>

    <f7-card class="post" outline no-shadow v-for="(post, index) in posts" :key="index">
      <f7-card-header style="margin: 5px auto;" class="no-hairline">
        <div class="post-user" >
          <img :src="post.owner" width="50" height="50" style="border-radius: 50%;"/>
          <div class="post-user-details">
            <span class="post-user-name">{{ post.by }}</span><br>
            <span class="post-time">02:20pm</span>
          </div>
        </div>
      </f7-card-header>
      <f7-card-content :padding="false" class="cardContent">
        <p>{{ post.para }}</p><img :src="post.image" width="100%"/>
        <p class="likes">Likes: 112 &nbsp;&nbsp; Comments: 43</p>
      </f7-card-content>
      <f7-block class="cardFooter">
        <f7-row>
          <f7-col>
            <f7-button class="cardFooterBtn" round small @click="like_status = !like_status">
              <f7-icon size="18" :f7="like_status ? 'hand_thumbsup_fill' : 'hand_thumbsup'"></f7-icon>
              <span>like</span>
            </f7-button>
          </f7-col>
          <f7-col>
            <f7-button class="cardFooterBtn" round small @click="comment_status = !comment_status">
              <f7-icon size="18" :f7="comment_status ? 'bubble_right_fill' : 'bubble_right'"></f7-icon>
              <span>comment</span>
            </f7-button>
          </f7-col>
          <f7-col>
            <f7-button class="cardFooterBtn" round small @click="share_status = !share_status">
              <f7-icon size="18" :f7="share_status ? 'arrowshape_turn_up_right_fill' : 'arrowshape_turn_up_right'"></f7-icon>
              <span>share</span>
            </f7-button>
          </f7-col>
        </f7-row>
      </f7-block>
    </f7-card>

    <f7-block strong>
      <p>This is an example of tabs-layout application. The main point of such tabbed layout is that each tab contains independent view with its own routing and navigation.</p>

      <p>Each tab/view may have different layout, different navbar type (dynamic, fixed or static) or without navbar like this tab.</p>
    </f7-block>

    <f7-block-title>Navigation</f7-block-title>
    <f7-list>
      <f7-list-item link="/about/" title="About"></f7-list-item>
      <f7-list-item link="/form/" title="Form"></f7-list-item>
      <f7-list-item link="/signin/" title="Login"></f7-list-item>
      <f7-list-item link="/signup/" title="Register"></f7-list-item>
    </f7-list>

    <f7-block-title>Modals</f7-block-title>
    <f7-block strong>
      <f7-row>
        <f7-col width="50">
          <f7-button fill raised popup-open="#my-popup">Popup</f7-button>
        </f7-col>
        <f7-col width="50">
          <f7-button fill raised login-screen-open="#my-login-screen">Login Screen</f7-button>
        </f7-col>
      </f7-row>
    </f7-block>

    <f7-list>
      <f7-list-item title="Dynamic (Component) Route" link="/dynamic-route/blog/45/post/125/?foo=bar#about"></f7-list-item>
      <f7-list-item title="Default Route (404)" link="/load-something-that-doesnt-exist/"></f7-list-item>
      <f7-list-item title="Request Data & Load" link="/request-and-load/user/123456/"></f7-list-item>
    </f7-list>

  </f7-page>
</template>

<script>
export default {
  data () {
    return {
      posts: [
        { owner: 'https://timesofindia.indiatimes.com/thumb/msid-66880878,imgsize-86155,width-800,height-600,resizemode-4/66880878.jpg', by: 'Dj Snake', para: 'Sun with moon!', image: 'https://image.shutterstock.com/image-photo/mountains-during-sunset-beautiful-natural-260nw-407021107.jpg' },
        { owner: 'https://cdn.europosters.eu/image/750/posters/avengers-endgame-i-am-iron-man-i76482.jpg', by: 'Iron Man', para: 'Amazing light combination...', image: 'https://i.pinimg.com/originals/42/d0/0c/42d00cfaf2cedabc7eac44e94d390c49.jpg' }
      ],
      like_status: false,
      comment_status: false,
      share_status: false
    }
  },
  methods: {
    hey() {
      console.log('icon')
    }
  }
}
</script>

<style scoped>
.post-user {
display: flex;
}
.post-user-details {
margin-left: 10px;
}
.post-user-name {
font-weight: 600;
}
.post-time {
color: grey;
font-size: 12px;
}
.navRight img {
  height: 40px;
  width: 40px;
  border-radius: 50%;
}
.post {
  margin: 0px;
  margin-bottom: 5px;
}
.post:last-child {
  margin: 0%;
}
.cardFooter {
  margin: 0px auto 10px auto;
}
.cardFooterBtn {
border: .5px solid;
}
p, .likes {
  margin: 10px 15px;
  margin-top: 5px;
}
</style>