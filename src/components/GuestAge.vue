<template>
  <h1>Sinh năm 1988 thì năm nay bao nhiêu tuổi?</h1>
  <div>
    <input type="text" v-model.number="inputAge" @keyup.enter="checkResult" />
    <button @click.prevent="checkResult">
      Kiểm tra
    </button>
  </div>
  <div>
    <h2>{{ messageResult }}</h2>
    <video
      v-if="flagResult"
      class="goodJob"
      src="https://video.fhan3-1.fna.fbcdn.net/v/t42.4659-2/125790246_3297835557012106_6721237388450607595_n.mp4?_nc_cat=102&ccb=2&_nc_sid=73e57b&_nc_ohc=3RZK_rutPRIAX9bb-Ru&_nc_ht=video.fhan3-1.fna&oh=cfa4c1412278606d9f85f675ebb88e9b&oe=5FC3A845"
      autoplay
      loop
    />
  </div>
</template>

<script>
import { ref } from "vue";
export default {
  setup() {
    const inputAge = ref("");
    const messageResult = ref("");
    const flagResult = ref(false);

    function checkResult() {
      const binZAge = 2020 - 1988;
      if (inputAge.value === binZAge) {
        flagResult.value = true;
        messageResult.value = "Amazing, good job em 👏";
      } else {
        flagResult.value = false;
        messageResult.value = "Em tính kiểu này thì chết anh rồi ☹️";
      }
    }

    return {
      inputAge,
      flagResult,
      checkResult,
      messageResult
    };
  }
};
</script>

<style>
input,
button {
  height: 2rem;
  font-size: 1.5rem;
}
button {
  margin-left: 1rem;
}
.goodJob {
  margin-top: 1rem;
}
</style>
