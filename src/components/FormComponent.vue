<template>
    <form @submit.prevent="submitForm">
        <div class="form-control">
            <label for="emp-name">ชื่อพนักงาน</label>
            <input type="text" v-model.trim="employee.name" required>
        </div>
        <div class="form-control">
            <label for="emp-salary">เงินเดือน</label>
            <input type="number" v-model="employee.salary" required>
        </div>
        <div class="form-control">
            <label for="emp-position" >ตำแหน่งงาน</label>
            <select v-model="employee.position" required>
                <option selected value="" >กรุณาเลือกตำแหน่งาน</option>
                <option value="Programmer">Programmer</option>
                <option value="Marketing">Marketing</option>
                <option value="Management">Management</option>
                <option value="Othur">Othur</option>
            </select>
        </div>
        <div class="form-control">
            <label for="gender">เพศ</label>
            <div>
                <input type="radio" value="Male" v-model="employee.gender" required>
                <label for="emp-gender">Male</label>
            </div>
            <div>
                <input type="radio" value="Female" v-model="employee.gender" required>
                <label for="emp-gender">Female</label>
            </div>
        </div>
        <div class="form-control">
            <label for="gender">ทักษะด้านภาษา</label>
            <div>
                <input type="checkbox" value="thai" v-model="employee.skill">
                <label for="emp-skill">ไทย</label>
            </div>
            <div>
                <input type="checkbox" value="englist" v-model="employee.skill">
                <label for="emp-skill">อังกฤษ</label>
            </div>
            <div>
                <input type="checkbox" value="japan" v-model="employee.skill">
                <label for="emp-skill">ญี่ปุ่น</label>
            </div>
        </div>
        <div>
            <button>บันทึกข้อมูล</button>
        </div>
    </form>

</template>

<script>
export default {
    name:"FormComponent",
    data(){
        return{
            employee:{
                name:"",
                salary:'',
                position:"",
                gender:"",
                skill:[]
            }
        }
    },
    methods:{
        submitForm(){
            const newEmployee={
                name:this.employee.name,
                salary:this.employee.salary,
                position:this.employee.position,
                gender:this.employee.gender,
                skill:this.employee.skill
            }
            this.$emit("save",newEmployee);
            this.resetForm();

        },
        resetForm(){
            this.employee.name="",
            this.employee.salary=0,
            this.employee.position="กรุณาเลือกตำแหน่งาน",
            this.employee.gender="",
            this.employee.skill=[]

        }
    }

}
</script>

<style scoped>
    form{
        margin: 2rem auto;
        max-width: 40rem;
        border-radius: 12px;
        box-shadow:0 2px 4px rgba(0,0,0,.25);
        padding: 2rem;
        background: beige;
    }
    .form-control{
        margin: .5rem 0;
    }
    label{
        font-weight: bold;
    }
    input, select{
        display: block;
        width: 100%;
        font: inherit;
        margin-top: .5rem;
        padding: 8px;
        border-radius: 10px;
    }
    button{
        font:inherit;
        background: goldenrod;
        cursor: pointer;
        color: white;
        border: none;
        padding: .5rem 1.5rem;
        border-radius: 15px;
    }
    input[type="radio"],input[type="checkbox"]{
        display: inline-block;
        width: auto;
        margin-right: 1rem;
    }
    input[type="radio"]+label,input[type="checkbox"]+label{
        font-weight: normal;
    }
    

</style>