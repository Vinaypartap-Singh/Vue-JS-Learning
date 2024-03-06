<!-- Data Binding in Vue JS -->

<template>
    <form @submit.prevent="handleSubmit">
        <input type="email" name="email" placeholder="Enter Your Email" v-model="email">
        <input type="password" name="password" placeholder="Enter Your Password" v-model="password">
        <select v-model="role">
            <option value="Web Developer">Web Developer</option>
            <option value="Web Designer">Web Designer</option>
            <option value="Backend Developer">Backend Developer</option>
        </select>
        <input type="checkbox" v-model="checked"> <label for="Accept The Terms"></label>

        <p v-if="checked">User Info - {{ email }} & {{ password }}</p>
        <p v-if="checked">Role: {{ role }}</p>
        <input type="submit" value="Submit" />
    </form>

</template>


<script>
export default {
    data() {
        return {
            email: "",
            password: "",
            role: "Web Developer",
            checked: false
        }
    },
    methods: {
        handleSubmit() {
            if (this.checked) {
                console.log(this.email)
                console.log(this.password)
                console.log(this.role)
                console.log(this.checked)
            } else {
                alert("terms and conditions")
            }

        }
    }
}
</script>