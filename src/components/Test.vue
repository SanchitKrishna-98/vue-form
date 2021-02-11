<template>
  <div id="visa">
    <h1>Enter Employee Details</h1>
    <form>
      <label for="full name">Full Name: </label>
      <input type="text" v-model="name" required><br>
      <br>

      <label for="email">Email ID:  </label>
      <input type="text" v-model="email" required> <br>
      <span v-if="msg.email">{{msg.email}}</span><br>

      <label for="password">Password: </label>
      <input type="password" v-model="password" required><br>
      <span v-if="msg.password">{{msg.password}}</span><br>

      <p>Gender:
      <input type="radio" id="male" name="gender" value="male">
      <label for="male">Male</label>
      <input type="radio" id="female" name="gender" value="female">
      <label for="female">Female</label>
      <input type="radio" id="other" name="gender" value="other">
      <label for="other">Other</label></p><br>

      <p>Years of Experience:
      <input type="checkbox" id="0-2yrs" name="exp" value="0-2yrs">
      <label for="0-2yrs">0-2years </label>
      <input type="checkbox" id="2-5yrs" name="exp" value="2-5yrs">
      <label for="2-5yrs">2-5years </label>
      <input type="checkbox" id="5+yrs" name="exp" value="5+yrs">
      <label for="5+yrs">5+years </label>
      </p><br>

      <label for="dep">Choose a department: </label>

      <select name="dep" id="dep">
      <option value="accounts">Accounts</option>
      <option value="developmet">Development</option>
      <option value="sales">Sales</option>
      <option value="hr">HR</option>
      </select>
      <br>
      <br>
      <button type="submit" value="Submit">Submit</button>

    </form>
  </div>
</template>

<script>
export default {
  name: 'Test',
  data(){
    return {
      name: '',
      email:null,
            reg: /^(([^<>()\]\\.,;:\s@"]+(\.[^<>()\]\\.,;:\s@"]+)*)|(".+"))@((\[[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}\.[0-9]{1,3}])|(([a-zA-Z\-0-9]+\.)+[a-zA-Z]{2,24}))$/,
      password: '',
      gender: '',
      experience: '',
      department:'',
      msg: [],
    }
  },
  watch: {
      email(value){
      this.email = value;
      this.validateEmail(value);
    },
    password(value){
      this.password = value;
      this.validatePassword(value);
    }
  },
  methods:{
  validateEmail(value){
  if(value== null || value == '')
{
  this.msg['email'] = "Please Enter Email";
}
else if(!this.reg.test(value))
{
  this.msg['email'] = "Please Enter Correct Email";
}
else{
  this.msg['email']='';
}
    },
    validatePassword(value){
      let difference = 8 - value.length;
      if (value.length<8) {
        this.msg['password'] = 'Must be 8 characters! '+ difference + ' characters left' ;
      } else {
        this.msg['password'] = '';
      }
    }
    
  }
}
</script>



<style >
#visa {
  margin: 20px auto;
  max-width: 700px;
  margin-bottom: 28px;
}
label{
  font-family: Arial, Helvetica, sans-serif ;
  margin: 20px 0 10px;
}
input {
  font-size: 25px;
  border: 1px double rgb(10, 3, 1) ;
  border-radius: 50px;
}
h1{
  font-family: cursive;
}
</style>