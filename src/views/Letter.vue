<template>
  <div class="letter row justify-content-center">
    <div class="col-md-6 col-sm-12 col-xs-12 content">
      <div class="header-content d-flex align-items-center justify-content-center" v-if="!isCreate">
        <div class="btn-send-letter button-56" role="button" @click="onCreate()">
          <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/icons/send-letter.gif" width="70px"
            alt="Send Letter" srcset="">
          <span>Put Your Message</span>
        </div>
      </div>
      <div class="break-area w-100 d-flex align-items-center justify-content-around my-5 py-5">
        <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/icons/Icon%201.png" alt="Send Letter"
          srcset="">
        <!-- <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/icons/Icon%202.png" alt="Send Letter" srcset=""> -->
        <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/icons/Icon%203.png" alt="Send Letter"
          srcset="">
        <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/icons/Icon%204.png" alt="Send Letter"
          srcset="">
      </div>
      <!-- LIST -->
      <div class="list-message" v-if="!isCreate">
        <div class="message-item d-flex align-items-center">
          <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/bash.png" width="100" alt="Send Letter"
            srcset="">
          <div class="right w-100">
            <h5 class="title">This is Title</h5>
            <p class="note">There will display description here</p>
            <p class="date">12:30 12/23/2024</p>
          </div>
        </div>
      </div>
      <!-- CREATE -->
      <div class="create-message" v-else>
        <div class="form-group px-2 mb-4">
          <input type="text" class="form-control" id="inputTitle" placeholder="Let's type title!">
        </div>
        <div class="form-group px-2 mb-4">
          <textarea class="form-control" id="inputNote" rows="5" placeholder="Let's type complain!"></textarea>
        </div>
        <div class="header-content d-flex align-items-center justify-content-center">
          <div class="btn-send-letter button-56" role="button" @click="onSendMessage()">
            <img src="https://storage.googleapis.com/ngongbabyandcoder.appspot.com/icons/send-letter.gif" width="70px"
              alt="Send Letter" srcset="">
            <span>Send Your Message</span>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';
import type { Message } from "@/interfaces/message";


const isCreate = ref<boolean>(false)
const itemMessage = ref({} as Message);

const onCreate = () => {
  isCreate.value = !isCreate.value
}

const onSendMessage = () => {

}

</script>

<style lang="scss">
.letter {
  background: #fff;
  height: 1000px;

  .content {
    background-color: mistyrose;
    padding-top: 20px;
    padding-left: 0;
    padding-right: 0;
    z-index: 0;
  }

  /* CSS */
  .button-56 {
    align-items: center;
    background-color: #fee6e3;
    border: 2px solid #111;
    border-radius: 8px;
    box-sizing: border-box;
    color: #111;
    cursor: pointer;
    display: flex;
    font-family: Inter, sans-serif;
    font-size: 16px;
    justify-content: center;
    line-height: 24px;
    max-width: 100%;
    padding: 0 25px;
    position: relative;
    text-align: center;
    text-decoration: none;
    user-select: none;
    -webkit-user-select: none;
    touch-action: manipulation;

    span {
      font-family: 'Caveat', cursive;
      font-family: 'Satisfy', cursive;
      margin-left: 12px;
    }
  }

  .button-56:after {
    background-color: #111;
    border-radius: 8px;
    content: "";
    display: block;
    height: 48px;
    left: 0;
    width: 100%;
    position: absolute;
    top: 24px;
    transform: translate(8px, 8px);
    transition: transform .2s ease-out;
    z-index: -1;
  }

  .button-56:hover:after {
    transform: translate(0, 0);
  }

  .button-56:active {
    background-color: #ffdeda;
    outline: 0;
  }

  .button-56:hover {
    outline: 0;
  }

  // BREAK
  .break-area {
    height: 50px;
    background-color: #fff;

    img {
      width: 80px;
      margin-top: 20px;
      cursor: pointer;
    }
  }

  // LIST MESSAGE 
  .list-message {
    .message-item {
      background-color: #fff;
      border-radius: 10px;
      padding: 15px 10px;
      margin-left: 20px;
      margin-right: 20px;
      box-shadow: 0px 10px 15px -3px rgba(0, 0, 0, 0.1);
      cursor: pointer;
      transition: 0.3s ease-in;

      &:hover {
        transform: scale(1.04);
      }

      .title {}

      .note {
        margin-bottom: 2px !important;
      }

      .date {
        margin-bottom: 0 !important;
        text-align: end;
        font-size: 12px;
        font-style: italic;
      }
    }
  }
}
</style>
