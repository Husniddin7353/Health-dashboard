<template>
  <div class="activity-table">
    <div class="table-header d-flex justify-content-between align-items-center">
      <h4 class="table-title">Appointment Activity</h4>
      <button class="add-btn" id="add-btn" @click="addDetail()">Add</button>
    </div>
    <table class="table">
      <tr class="heading-row">
        <th></th>
        <th class="first-heading">Name</th>
        <th>Email</th>
        <th>Date</th>
        <th>Visit Time</th>
        <th>Doctor</th>
        <th>Conditions</th>
        <th></th>
      </tr>
      <tr
        class="td-row"
        v-for="(element, index) in this.tableInfo"
        :key="index"
      > 
        <td class="profile-img">
          <img :src="element.img" alt="" />
          </td> 
        <td class="td-row__item">
          {{ element.namee }}
        </td>
        <td class="td-row__item">{{ element.email }}</td>
        <td class="td-row__item">{{ element.date }}</td>
        <td class="td-row__item">{{ element.visitTime }}</td>
        <td class="td-row__item">{{ element.doctor }}</td>
        <td class="td-row__item">{{ element.conditions }}</td>
        <td>
          <button class="edit btn td-row__item" @click="edit(element, index)">
            <svg
              width="16"
              height="16"
              viewBox="0 0 16 16"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M0 15.3664C0.4448 13.84 0.888 12.3136 1.3328 10.7872C1.368 10.6656 1.4048 10.544 1.4368 10.4224C1.488 10.2384 1.584 10.0896 1.7312 9.9664C1.8688 9.8528 1.9904 9.7168 2.1168 9.5904C4.2016 7.5248 6.2864 5.45921 8.3696 3.39201C8.4176 3.34401 8.4592 3.28961 8.4928 3.24801C8.776 3.53281 9.0416 3.80001 9.3376 4.09761C9.3056 4.12001 9.2432 4.15201 9.1952 4.20001C7.0352 6.35521 4.8768 8.5104 2.7216 10.6704C2.6448 10.7488 2.5808 10.856 2.5504 10.9616C2.2912 11.8176 2.0448 12.6784 1.7888 13.5376C1.7568 13.6448 1.7728 13.712 1.8544 13.7856C1.9872 13.9056 2.104 14.0432 2.2384 14.1616C2.2848 14.2016 2.3728 14.232 2.4288 14.2176C3.2896 13.9712 4.1488 13.72 5.0064 13.4608C5.08 13.4384 5.1488 13.376 5.2064 13.3168C7.3968 11.1328 9.584 8.9456 11.7712 6.76001C11.8128 6.71841 11.848 6.67201 11.872 6.64481C12.1824 6.95521 12.4832 7.256 12.8128 7.5856C12.7984 7.5952 12.7408 7.6192 12.7008 7.6592C10.544 9.7952 8.384 11.9264 6.2384 14.0736C5.9392 14.3744 5.6144 14.56 5.2128 14.6736C3.7888 15.0768 2.3712 15.5024 0.9504 15.92C0.856 15.9472 0.76 15.9728 0.6656 16H0.5376C0.4688 15.9696 0.3984 15.9424 0.3296 15.9104C0.1376 15.8208 0.072 15.6384 0 15.4608V15.3664ZM4.3024 12.7152C4.2608 12.4496 4.216 12.2064 4.1872 11.9632C4.1728 11.848 4.1264 11.8016 4.0144 11.7808C3.7408 11.728 3.4704 11.6592 3.2176 11.6032C5.4864 9.3296 7.7552 7.05441 10.0096 4.79361C10.3696 5.15361 10.7456 5.52801 11.1088 5.88961C8.8624 8.1424 6.5952 10.416 4.3024 12.7152ZM10.8368 1.02562C11.0416 0.825621 11.2464 0.612821 11.4656 0.414422C12.0944 -0.151977 12.9136 -0.139177 13.5264 0.459222C14.2032 1.11842 14.8704 1.78562 15.5296 2.46242C16.1536 3.10082 16.144 3.95521 15.5216 4.59201C15.3344 4.78401 15.1408 4.97121 14.9616 5.14721C13.592 3.77921 12.224 2.41282 10.8368 1.02562ZM9.168 2.53602C9.4784 2.24482 9.7968 1.94562 10.0992 1.66082C11.5328 3.09442 12.9584 4.52161 14.3968 5.96001C14.0976 6.24001 13.776 6.54241 13.4656 6.83361L9.168 2.53602Z"
                fill="#A0A4A8"
              />
            </svg>
          </button>
          <button class="delete btn td-row__item" @click="remove(element)">
            <svg
              width="12"
              height="14"
              viewBox="0 0 12 14"
              fill="none"
              xmlns="http://www.w3.org/2000/svg"
            >
              <path
                d="M2.00952 13.3248C2.02552 13.7024 2.33592 14 2.71352 14H9.29112C9.66872 14 9.98072 13.7024 9.99512 13.3248L10.4655 3.408H1.53912L2.00952 13.3248ZM7.48952 5.872C7.48952 5.7136 7.61752 5.5856 7.77592 5.5856H8.23352C8.39192 5.5856 8.51992 5.7152 8.51992 5.872V11.5376C8.51992 11.696 8.39032 11.824 8.23352 11.824H7.77592C7.61752 11.824 7.48952 11.696 7.48952 11.5376V5.872ZM5.48792 5.872C5.48792 5.7136 5.61592 5.5856 5.77432 5.5856H6.23192C6.39032 5.5856 6.51832 5.7152 6.51832 5.872V11.5376C6.51832 11.696 6.39032 11.824 6.23192 11.824H5.77432C5.61592 11.824 5.48792 11.696 5.48792 11.5376V5.872ZM3.48472 5.872C3.48472 5.7136 3.61272 5.5856 3.76952 5.5856H4.22712C4.38552 5.5856 4.51352 5.7152 4.51352 5.872V11.5376C4.51352 11.696 4.38392 11.824 4.22712 11.824H3.76952C3.61112 11.824 3.48472 11.696 3.48472 11.5376V5.872ZM10.7775 0.7216H7.74392V0.1472C7.74392 0.0656 7.67832 0 7.59672 0H4.40952C4.32792 0 4.26232 0.0656 4.26232 0.1472V0.7216H1.22712C0.983922 0.7216 0.785522 0.9184 0.785522 1.1632V2.552H11.2191V1.1632C11.2191 0.92 11.0223 0.7216 10.7775 0.7216V0.7216Z"
                fill="#FF6760"
              />
            </svg>
          </button>
        </td>
      </tr>
    </table>

    <div :class="isActive ? 'openModal' : ''" class="modal-wrapper">
      <div class="table-modal">
        <h4 class="modal_title">Add Activity</h4>
        <form
          onsubmit="return false"
          :class="{
            'is-invalid': $v.form.$error,
          }"
        >
          <div class="row">
            <div class="col-md-6 mt-3">
              <label for="name"> Name</label>
              <input
                type="text"
                id="name"
                placeholder="Enter Name"
                v-model="form.namee"
                required
                :class="{
                  invalid: $v.form.namee.$model,
                }"
              />
            </div>
            <div class="col-md-6 mt-3">
              <label for="email"> Email</label>
              <input
                type="email"
                placeholder="Enter Email"
                id="email"
                v-model="form.email"
                required
                :class="{
                  invalid: $v.form.email.$model,
                }"
              />
            </div>
            <div class="col-md-6 mt-3">
              <label for="date"> Date</label>
              <input
                type="text"
                v-mask="'##/##/####'"
                placeholder="dd/mm/yyyy"
                id="date"
                v-model="form.date"
                required
                :class="{
                  invalid: $v.form.date.$model,
                }"
              />
            </div>
            <div class="col-md-6 mt-3">
              <label for="time"> Time</label>
              <input
                type="text"
                placeholder="00:00-00:00pm"
                v-mask="'##:##-##:## AA'"
                id="time"
                v-model="form.time"
                required
                :class="{
                  invalid: $v.form.time.$model,
                }"
              />
            </div>
            <div class="col-md-6 mt-3">
              <label for="doctor"> Doctor</label>
              <input
                type="text"
                placeholder="Enter Doctor name"
                id="doctor"
                v-model="form.doctor"
                required
                :class="{
                  invalid: $v.form.doctor.$model,
                }"
              />
            </div>
            <div class="col-md-6 mt-3">
              <label for="conditions"> Conditions</label>
              <input
                type="text"
                placeholder="Enter Conditions"
                id="conditions"
                v-model="form.conditions"
                required
                :class="{
                  invalid: $v.form.conditions.$model,
                }"
              />
            </div>
            <div class="modal-buttons d-flex justify-content-end">
              <button class="cancel" @click="cancel()">Cancel</button>
              <button class="add" @click="addInfo()">Add</button>
              <pre>{{ this.form[0].$model }}</pre>
            </div>
          </div>
        </form>
      </div>
    </div>
  </div>
</template>
<script>
import { required } from "vuelidate/lib/validators";
export default {
  name: "Activity",
  data() {
    return {
      addButton: false,
      a: null,

      isActive: false,
      element: [],
      form: [
        {
          img: require("../assets/profile1.png"),
          namee: "",
          email: "",
          time: "",
          date: "",
          doctor: "",
          conditions: "",
        },
      ],

      tableInfo: [
        {
          id: 0,
          img: require("../assets/profile1.png"),
          namee: "Leslie Alexander",
          email: "lesie.alexander@example.com",
          date: "10/10/2020",
          visitTime: "09:15-09:45am",
          doctor: "Dr. Jacob Jones",
          conditions: "Mumps Stage II",
        },
        {
          id: 1,
          img: require("../assets/profile2.png"),
          namee: "Ronald Richards",
          email: "ronald.richards@example.com",
          date: "10/10/2020",
          visitTime: "12:00-12:45pm",
          doctor: "Dr. Theresa Webb",
          conditions: "Depression",
        },
        {
          id: 2,
          img: require("../assets/profile3.png"),
          namee: "Jane Cooper",
          email: "jane.cooper@example.com",
          date: "10/13/2020",
          visitTime: "01:15-01:45pm",
          doctor: "Dr. Jacob Jones",
          conditions: "Arthritis",
        },
        {
          id: 3,
          img: require("../assets/profile4.png"),
          namee: "Robert Fox",
          email: "robert.fox@gmail.com",
          date: "10/14/2020",
          visitTime: "02:00-02:45pm",
          doctor: "Dr. Arlene McCoy",
          conditions: "Fracture",
        },
        {
          id: 4,
          img: require("../assets/profile2.png"),
          namee: "Jenny Wilson",
          email: "jenny.wilson@example.com",
          date: "10/15/2020",
          visitTime: "12:00-12:45pm",
          doctor: "Dr. Esther Howard",
          conditions: "Depression",
        },
      ],
    };
  },
  validations: {
    form: {
      namee: {
        required,
      },
      email: {
        required,
      },
      date: {
        required,
      },
      time: {
        required,
      },
      doctor: {
        required,
      },
      conditions: {
        required,
      },
    },
  },

  methods: {    
    addDetail() {
      this.isActive = true;
      this.addButton = true;
    },

    cancel() {
      this.isActive = false;
    },

    remove(element) {
      const id = element.id;
      const index = this.tableInfo.findIndex((x) => x.id === id);
      this.tableInfo.splice(index, 1);
    },

    edit(element, index) {
      this.isActive = true;      
      this.form.namee = element.namee;
      this.form.email = element.email;
      this.form.date = element.date;
      this.form.time = element.time;
      this.form.doctor = element.doctor;
      this.form.conditions = element.conditions;
      this.a = index;
    },

    addInfo() {
      if (this.addButton === true) {
        if (this.$v.form.$invalid) {
          this.$v.form.$touch();
        } else {
          this.tableInfo.push({
            img: this.form[0].img,
            namee: this.$v.form.namee.$model,
            email: this.$v.form.email.$model,
            date: this.$v.form.date.$model,
            visitTime: this.$v.form.time.$model,
            doctor: this.$v.form.doctor.$model,
            conditions: this.$v.form.conditions.$model,
          });
          this.isActive = false;
          this.addButton = false;

          (this.$v.form.namee.$model = ""),
            (this.$v.form.email.$model = ""),
            (this.$v.form.date.$model = ""),
            (this.$v.form.time.$model = ""),
            (this.$v.form.doctor.$model = ""),
            (this.$v.form.conditions.$model = "");
        }
      } else {                
        if (this.$v.form.$invalid) {
          this.$v.form.$touch();
        } else {
            this.tableInfo.splice(this.a, 1, {
            img: this.form[0].img,
            namee: this.$v.form.namee.$model,
            email: this.$v.form.email.$model,
            date: this.$v.form.date.$model,
            visitTime: this.$v.form.time.$model,
            doctor: this.$v.form.doctor.$model,
            conditions: this.$v.form.conditions.$model,
          })          
          this.isActive = false;
          this.addButton = false;

          (this.$v.form.namee.$model = ""),
            (this.$v.form.email.$model = ""),
            (this.$v.form.date.$model = ""),
            (this.$v.form.time.$model = ""),
            (this.$v.form.doctor.$model = ""),
            (this.$v.form.conditions.$model = "");
        }
      }
    },
  },
};
</script>
<style lang="scss">
.openModal {
  display: block !important;
}

td {
  font-family: Lato, sans-serif;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.1px;
  color: #52575c;
  padding: 12px 0;
  border: none !important;

  img {
    padding: 0;
    margin-right: 12px;
  }
}

th {
  font-family: Lato, sans-serif;
  font-weight: bold;
  font-size: 14px;
  line-height: 20px;
  letter-spacing: 0.1px;
  color: #25282b;
}

.activity-table {
  background: #ffffff;
  box-shadow: 0px 12px 26px rgba(16, 30, 115, 0.06);
  border-radius: 8px;

  .modal-wrapper {
    display: none;
    position: fixed;
    width: 100%;
    height: 100vh;
    background: rgba(0, 0, 0, 0.562);
    top: 0;
    left: 0;

    .table-modal {
      padding: 16px 24px;
      background: #ffffff;
      box-shadow: 0px 0px 1px rgba(12, 26, 75, 0.24),
        0px 3px 8px -1px rgba(50, 50, 71, 0.05);
      border-radius: 6px;
      position: fixed;
      top: 52%;
      left: 50%;
      transform: translate(-50%, -50%);
      transition: all 0.3s;

      input {
        width: 100%;
        background: #ffffff;
        border: 1px solid #e4e6ef;
        box-sizing: border-box;
        border-radius: 6px;
        font-family: Inter;
        font-size: 14px;
        line-height: 14px;
        color: #000;
        outline: none;
        padding: 10px 12px;
      }

      label {
        font-family: Inter, sans-serif;
        font-size: 13px;
        line-height: 19px;
        color: #3f4254;
      }

      .modal-buttons {
        button {
          border-radius: 6px;
          padding: 9px 24px;
          font-family: Inter, sans-serif;
          font-size: 12px;
          outline: none;
          line-height: 19px;
          margin-top: 32px;
        }

        .cancel {
          background: #e4e6ef;
          border: 1px solid #e4e6ef;
          color: #3f4254;
        }

        .add {
          background: #3699ff;
          color: #ffffff;
          border: 1px solid #3699ff;
          margin-left: 12px;
        }
      }
    }
  }

  .table-header {
    padding: 24px;

    .add-btn {
      background: #30a6f5;
      border-radius: 4px;
      color: #fff;
      border: 1px solid #30a6f5;
      outline: none;
      font-size: 13px;
      padding: 4px 12px;
      transition: all 0.3s;
    }

    .add-btn:hover {
      background: #0c5f96cb;
    }
  }

  .table-title {
    font-family: Lato, sans-serif;
    font-weight: bold;
    font-size: 20px;
    line-height: 26px;
    letter-spacing: 0.2px;
    color: #25282b;
    margin: 0;
  }

  .table {
    .heading-row {
      background: #e8e8e869;
      padding: 19px 0;
      width: 100%;

      .add {
        border: 1px solid #30a6f5;
        background: #558effa9;
        padding: 2px 8px;
        border-radius: 8px;
        color: #fff;
        transition: all 0.3s;
      }

      .add:active {
        background: #558eff;
      }

      .first-heading {
        padding-left: 24px;
      }

      th {
        padding: 18px 0;
        padding-left: 10px;
      }
    }

    .td-row {
     
      transition: all 0.2s;
      
      td:first-child {
        padding-left: 24px;
      }

     &__item{
       padding-top: 4%;
     }

     .btn{
       padding-top: 20px;
     }

      .edit,
      .delete {
        border: none;
        border-radius: 4px;
      }

      .edit:hover,
      .delete:hover {
        background: #e0e0e05e;
      }
    }

    .td-row:hover {
      background: #e8e8e85b;
    }
  }
}
</style>
