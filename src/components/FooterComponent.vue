<template>
    <div class="footer">
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css">
    <div class="footer-links">
      <label>Email:</label>
      <a> hospitalmanagement@gmail.com</a>
    </div>
    <div class="footer-links">
      <label>Phone:</label>
      <a> 1234567890</a>
    </div>
    <div class="foot-copyright">
        <span><i class="fa fa-copyright"> Hospital Management 2022</i></span>
    </div>
  </div>
</template>

<script>

export default {
    name: "FooterComponent"
}
</script>

<style>
  
  .footer {
    background-color: #40dd6d;
    color: white;
    height: 150px;
    margin: 10px;
    padding: 10px;
  }
  .foot-copyright {
    font-size: 20px;
    text-align: center;
    margin-top: 80px;
  }

  .footer-links {
    text-align: center;
    margin: 5px;
  }
</style>