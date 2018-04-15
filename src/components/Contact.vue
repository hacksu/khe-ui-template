<template>
  <div id="contact" class="widget">
    <h2 id="contactTitle">Contact us</h2>
    <p>
      If you have any questions, concerns, or problems, please do not hesitate to contact us. One of our organizers will get back to you as soon as humanly possible.
    </p>
    <div class="formField">
      <span>Subject:</span>
      <input type="text" placeholder="Ex: Team Formation" name="subject"
             class="contactTextField"
             v-model="subject">
    </div>
    <div class="formField">
      <span>Name:</span>
      <input type="text" placeholder="Ex: John Doe" name="name"
             class="contactTextField"
             v-model="name">
    </div>
    <div class="formField">
      <span>Email:</span>
      <input type="text" placeholder="Ex: jdoe@example.com" name="email"
             class="contactTextField"
             v-model="email">
    </div>
    <div class="formField">
      <span>Body:</span>
      <textarea placeholder="Tell us what's up here!" name="body"
             class="contactTextField"
             v-model="content">
      </textarea>
    </div>
    <button id="contactButton" 
            class="apply-link"
            @click="submitTicket()">
      Send!
    </button>
  </div>
</template>

<style scoped>

  #infoTitle {
    font-size: 50px;
  }

  #contact {
    background: black;
    font-size: 20px;
    line-height: 30px;
    height: 100vh;
    color: white;
  }
  
  .formField {
    width: 100%;
    margin-bottom: 20px;
  }
  .contactTextField {
    display: block;
    color: white;
    background: none;
    border: none;
    outline: none;
    font-size: 20px;
    width: 100%;
    border-bottom: 2px solid white;
  }
  
  #contactButton {
    cursor: pointer;
    outline: none;
    width: 200px;
    height: 50px;
    font-size: 20px;
    border-bottom-left-radius: 10% 50%;
    border-bottom-right-radius: 10% 50%;
    border-top-left-radius: 10% 50%;
    border-top-right-radius: 10% 50%;
  }
  #contactButton:active {
    background: black;
    color: white;
  }
</style>

<script>


export default {
  name: 'Main',
  data() {
    return {
      subject: '',
      name: '',
      email: '',
      content: '',
    };
  },
  methods: {
    submitTicket() {
      this.$parent.wrapper.ticketManager.submitTicket(this.subject,
          this.content,
          this.email,
          this.name)
        .then((data) => {
          // TODO: Show ticket created success.
          console.log(data);
        })
        .catch((err) => {
          // TODO: Show ticket creation error.
          throw err;
        });
    }
  }
};
</script>
