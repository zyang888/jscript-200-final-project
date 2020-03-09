<template>
  <div class="container">
    <h1>Connect With Us</h1>
    <form id="connect-form" @submit="checkForm" method="post" novalidate="true">
      <p v-if="errors.length">
    <b>Please correct the following error(s):</b>
    <ul>
      <li v-for="error in errors">{{ error }}</li>
    </ul>
  </p>
      <div class="form-group">
        <label for="first-name">First Name</label>
        <input class="form-control validate-input" type="text" name="first-name" v-model="first" required minlength="3" />
        <small class="error" aria-live="polite"></small>
      </div>

      <div class="form-group">
        <label for="last-name">Last Name</label>
        <input class="form-control validate-input" type="text" name="last-name" v-model="last" required minlength="3" />
        <small class="error" aria-live="polite"></small>
      </div>

      <div class="form-group">
        <label for="email">Email</label>
        <input class="form-control validate-input" type="email" name="email" v-model="email" />
        <small class="error" aria-live="polite"></small>
      </div>

      <div class="form-group">
        <label for="kind">What can we help with?</label>
        <select class="form-control validate-input" name="kind" id="contact-kind" v-model="contact" required>
          <option value="choose" selected="selected" disabled>Choose one</option>
          <option value="business">I'm interested in your software</option>
          <option value="technical">I need technical support</option>
        </select>
        <small class="error" aria-live="polite"></small>
      </div>

      <div v-show="contact=='business'" class="form-group business">
        <label for="company-size">Number of people in company</label>
        <input class="form-control validate-input" type="number" name="company-size" required />
        <small class="error" aria-live="polite"></small>
      </div>

      <div v-show="contact=='technical'" class="form-group technical">
        <label for="support-type">What software are you using</label>
        <input class="form-control validate-input" type="number" name="company-size" required />
        <small class="error" aria-live="polite"></small>
      </div>

      <div class="form-check mb-3">
        <input class="form-check-input" type="checkbox" name="yes-newsletter" />
        <label class="form-check-label" for="yes-newsletter">Join Newsletter?
        </label>
      </div>

      <div class="form-group">
        <input class="btn btn-primary" type="submit" value="Sign up" />
      </div>
    </form>
  </div>
</template>

<script>

export default {
  name: 'formpage',
  data() {
    return {
      errors: [],
      first: null,
      last: null,
      email: null,
      contact: null
    }
  },
  methods: {
    checkForm: function (e) {
      this.errors = [];
      if (!this.first) {
        this.errors.push("Name required.");
      }
      if (!this.email) {
        this.errors.push('Email required.');
      } else if (!this.validEmail(this.email)) {
        this.errors.push('Valid email required.');
      }
      e.preventDefault();
    },
    validEmail: function (email) {
      return /\w+@\w+\.\w+/.test(email);
    }
  }

}
</script>

<style>
textarea:invalid,select:invalid,input:invalid {
  border: 2px solid red;
box-shadow: 2px 2px 5px orangered;
}

textarea:valid,select:valid,input:valid {
border: 1px solid forestgreen;
}

.error {
  color: red;
}

</style>
