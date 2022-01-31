<template>
  <div class="lockscreen"  v-if="isLocked">
    <div class="lock-form">
      <h2>Welcome, User💻</h2>
      <form @submit.prevent>
        <div>
          <label>Password: </label>
          <input
            type="password"
            class="password"
            placeholder="••••"
            v-model="inputPin"
          />
          <p v-if="wrongPin">Wrong Password. Try 1111😉</p>
        </div>
        <button class="btn-enter" @click="dis">Enter</button>
      </form>
    </div>
  </div>
</template>

<script>
export default {
  emits:['disableLock'],
  data() {
    return {
      isLocked: true,
      wrongPin: false,
      inputPin: null,
    };
  },
  // provide:{lockedStatus: this.isLocked},
  methods: {
    dis() {
      if (this.inputPin === '1111' || this.inputPin === '2123') {
        this.isLocked = false;
        this.wrongPin = false;
        this.inputPin = '';
        this.$emit('disableLock')
      } else {
        this.wrongPin = true;
        this.inputPin = '';
      }
    },
  },
};
</script>

<style>
.lockscreen {
  display: block;
  position: absolute;
  height: 100vh;
  width: 100%;
  z-index: 11;
  color: white;
  background-color: rgba(29, 29, 29, 0.925);
}
.lock-form {
  position: absolute;
  display: block;
  text-align: center;
  left: 50%;
  top: 50%;
  transform: translate(-50%, -50%);
  z-index: 12;
  font-size: 1rem;

  animation-name: lockShow;
  animation-duration: 0.5s;
  animation-timing-function: ease-out;
}
.password {
  border-style: none;
  border-radius: 10px;
  padding: 10px;
  background-color: rgba(119, 119, 119, 0.425);
  color: rgb(196, 196, 196);
}
.btn-enter {
  color: white;
  background-color: rgba(119, 119, 119, 0.425);
  border-style: none;
  border-radius: 100px;
  padding: 10px 30px;
  font-family: inherit;
  font-weight: 900;
  margin-top: 1.5rem;
  transition: 0.2s all;
}
.btn-enter:hover {
  transform: scale(1.05);
}

.btn-enter:active {
  transform: translateY(2px);
}

h2 {
  font-size: 2rem;
}
</style>
