<template>
  <ul class="list-of-apps">
    <li v-for="app in apps" :key="app.id">
      <a :href="app.link" :class="app.link" :onclick="app.type">
        <img
          :src="require(`@/assets/${app.source}`)"
          :alt="app.name"
          class="desk-item"
        />
        <h3>{{ app.name }}</h3>
      </a>
    </li>
  </ul>
</template>

<script>

export default {
  props: ['id', 'name', 'source'],
  data() {
    return {
      apps: [
        {
          id: 'finder',
          name: 'Finder',
          source: 'finder.png',
        },
        {
          id: 'settings',
          name: 'Settings',
          source: 'settings.png',
        },
        {
          id: 'youtube',
          name: 'YouTube',
          source: 'youtube.png',
          link: 'https://www.youtube.com/',
          class: 'open-link',
        },
        {
          id: 'music',
          name: 'Music',
          source: 'music.png',
        },
        {
          id: 'telegram',
          name: 'Telegram',
          source: 'telegram.png',
          link: 'https://web.telegram.org/',
          class: 'open-link',
        },
      ],
    };
  },
};
</script>

<style scoped>
#list-of-apps {
  position: absolute;
  display: block;
  z-index: 2;
}

li {
  color: #fff;
  padding: 7px;
  transition: all 0.2s;
}
li:hover {
  background-color: rgba(119, 119, 119, 0.24);
  transform: scale(1.05);
}
ul {
  list-style: none;
}
a {
  text-decoration: none;
  color: white;
}
img {
  display: block;
  margin: 0 auto;
}
h3 {
  font-size: 0.9rem;
  text-align: center;
  margin: 0;
  padding-top: 5px;
  padding-bottom: 7px;
}

.desk-item {
  height: 50px;
}
</style>
>
