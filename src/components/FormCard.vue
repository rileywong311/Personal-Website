<template>
  <div style="background: var(--background2); border-radius: 50px; padding: 50px min(50px, 5vw) 50px; width: min(500px, 80vw);">
    <form ref="form" style="display: flex; flex-wrap: wrap; gap: 20px"
          action="https://formsubmit.co/5c607dcce256a2552b8de66e7fc569bb" method="POST">
    <input type="text" name="_honey" style="display:none">
    <input type="hidden" name="_captcha" value="false">
    <input type="hidden" name="_next" :value="this.url + '/received'">
    <input type="hidden" name="_subject" value="New website submission">
      <span>
        <h4 class="required"><label for="First">First name:</label></h4>
        <input name="name" id="First" type="text" placeholder="Enter your first name" required style="width: min(175px, 55vw)">
      </span>
      <span>
        <h4><label for="Last">Last name:</label></h4>
        <input name="last&nbsp;name" id="Last" type="text" placeholder="Enter your last name" style="width: min(175px, 55vw)">
      </span>
      <span>
        <h4 class="required"><label for="Email">Email:</label></h4>
        <input name="email" id="Email" type="email" placeholder="Enter your email" style="width: min(475px, 75vw)">
      </span>
      <span>
        <h4 class="required"><label for="Message">Message:</label></h4>
        <textarea name="message" id="Message" placeholder="Ex) You're website is so cool!" required rows="5" cols="999" style="max-width: min(475px, 75vw); max-height: 300px"></textarea>
      </span>
      <input type="submit" class="submit-button shadow" value="Submit">
    </form>
    <!-- <dialog ref="dialog" class="dialog" @click="closeDialog">
      <h3 style="font-weight: 300;">Recieved. <span style="color: var(--secondary); font-weight: 500;">Thank you!</span></h3>
    </dialog> -->
  </div>
</template>


<script>
import { URL_NAME } from '@/myurl.js';

export default {
  name: 'FormCard',
  data: () => {
    return {
      url: URL_NAME,
    }
  }
}
</script>


<style scoped>
input,
textarea {
  margin-top: 5px;
  padding: 7.5px;
  border: 1px solid rgb(174, 174, 174);
  border-radius: 10px;
  font-family: 'Lexend', sans-serif, system-ui;;
  font-weight: 300;
}

.submit-button {
  font-family: 'Lexend', sans-serif, system-ui;;
  font-weight: 300;
  background: var(--secondary);
  font-size: 1rem;
  color: white;
  transition: 0.25s;
  margin-top: auto;
  margin-right: auto;
  padding: 7.5px 20px 7.5px;
  border: 1px solid rgb(174, 174, 174);
  border-radius: 10px;
}

.submit-button:hover {
  transform: scale(1.07);
  cursor: pointer;
}

.required::after {
  content: ' *';
  color: red;
  vertical-align: text-top;
}

</style>