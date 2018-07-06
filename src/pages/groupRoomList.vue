<template>
    <div class="content">
        <headerCom  :text="text"/>
        <div class="part-1">
           <div class="time-filter">
              <span>选择时间</span>
              <div class="select">
                <!-- <input id="txtSearchDate" type="text" class="p-date" readonly> -->
                <date-picker :date="startTime" :option="option" id="select_date"></date-picker>
              </div>
           </div>
           <div class="time-filter">
              <span>游戏类别</span>
              <div class="select">
                <select name="selectGame" id="selectGame">
                  <option selected="selected" value="0" name="gameType">青岛麻将</option>
                  <option value="1">威海麻将</option>
                  <option value="2">烟台麻将</option>
                </select>
              </div>
           </div>
        </div>
        <div class="part-2">
          <table>
            <thead>
              <tr>
                <td>开房时间</td>
                <td>玩家名称</td>
                <td>房间战绩</td>
                <td>房间状态</td>
              </tr>
            </thead>
            <tbody id="divInfo">
					</tbody>
				</table>
        </div>
        <FooterCom />
    </div>
</template>
<script>
import HeaderCom from "@/components/Header";
import FooterCom from "@/components/Footer";
import $ from "jquery";
import myDatepicker from "vue-datepicker/vue-datepicker-es6.vue";
export default {
  name: "groupRoomList",
  data() {
    return {
      text: "房间列表",
      startTime: {
        time: ""
      },
      endTime: {
        time: ""
      },
      option: {
        type: "day",
        week: ["Mo", "Tu", "We", "Th", "Fr", "Sa", "Su"],
        month: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July",
          "August",
          "September",
          "October",
          "November",
          "December"
        ],
        format: "YYYY-MM-DD",
        placeholder: "when?",
        inputStyle: {
          display: "inline-block",
          padding: "4px",
          "line-height": "17px",
          "font-size": "14px",
          width: "190px",
          border: "1px solid #ddd",
          // 'box-shadow': '0 1px 3px 0 rgba(0, 0, 0, 0.2)',
          "border-radius": "5px",
          color: "#5F5F5F"
        },
        color: {
          header: "#ccc",
          headerText: "#f00"
        },
        buttons: {
          ok: "Ok",
          cancel: "Cancel"
        },
        overlayOpacity: 0.5, // 0.5 as default
        placeholder: '请选时间',
        dismissible: true // as true as default
      },
      timeoption: {
        type: "min",
        week: ["Mo", "Tu", "We", "Th", "Fr", "Sa", "Su"],
        month: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July",
          "August",
          "September",
          "October",
          "November",
          "December"
        ],
        format: "YYYY-MM-DD HH:mm"
      },
      multiOption: {
        type: "multi-day",
        week: ["Mo", "Tu", "We", "Th", "Fr", "Sa", "Su"],
        month: [
          "January",
          "February",
          "March",
          "April",
          "May",
          "June",
          "July",
          "August",
          "September",
          "October",
          "November",
          "December"
        ],
        format: "YYYY-MM-DD HH:mm"
      },
    };
  },
  mounted() {},
  methods: {},
  components: {
    HeaderCom,
    FooterCom,
    "date-picker": myDatepicker
  }
};
</script>
<style lang="less" scoped>
@import "../../static/css/global.css";
.part-1 {
  margin: 0 2rem;
  .time-filter {
    display: -webkit-box;
    display: -webkit-flex;
    display: -moz-box;
    display: -ms-flexbox;
    display: flex;
    margin-top: 1.5rem;
    margin-bottom: 1rem;
    justify-content: center;
    align-items: center;
    span {
      color: #fff;
      margin-right: 1rem;
    }
    .select {
      position: relative;
      display: inline-block;
      border: solid 1px #fff;
      border-radius: 5px;
      // .date-picker{

      // }
      .cov-vue-date {
        width: 10rem;
        height: 2rem;
        line-height: 2rem;
        text-align: center;
        box-sizing: border-box;
        background: none;
        border: none;
        color: #fff;
        .datepickbox{
          
        }
      }
      select {
        width: 10rem;
        height: 2rem;
        line-height: 0.2rem;
        text-align: center;
        box-sizing: border-box;
        background: none;
        border: none;
        color: #fff;
      }
    }
  }
}
.part-2 {
  margin: 0 2rem;
  table {
    width: 100%;
    color: #fff;
    background: url(../../static/img/border-v.png) left center no-repeat,
      url(../../static/img/border-v.png) right center no-repeat;
    background-size: 0.2rem 85%;
    thead {
      tr {
        padding: 2rem 0;
        background-image: -webkit-linear-gradient(90deg, #00001a, #1a0e32);
      }
    }
    tr {
      display: flex;
      width: 100%;
      td {
        flex: 1;
        text-align: center;
      }
    }
  }
}
</style>


