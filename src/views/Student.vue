<template>
  <div style="margin: 10% 20% 20px 20%">
    <el-button
      style="float: right"
      type="primary"
      icon="far fa-plus"
      @click="dialogFormVisible = true"
      >Thêm mới</el-button
    >
    <el-dialog
      title="Thông tin học sinh mới  "
      :visible.sync="dialogFormVisible"
    >
      <el-form :model="form" class="row">
        <div class="col-lg-5">
          <div class="block">
            <el-form-item label="Ngày sinh">
              <el-date-picker
                v-model="value1"
                type="datetime"
                placeholder="Chọn ngày sinh của bạn ..."
              >
              </el-date-picker>
            </el-form-item>
          </div>
        </div>
        <div class="col-lg-5">
          <el-form-item label="Chọn lớp">
            <el-select v-model="value" placeholder="Chọn lớp học của bạn ...">
              <el-option
                v-for="item in options"
                :key="item.value"
                :label="item.label"
                :value="item.value"
              >
              </el-option>
            </el-select>
          </el-form-item>
        </div>
      </el-form>
      <span slot="footer" class="dialog-footer">
        <el-button @click="dialogFormVisible = false">Cancel</el-button>
        <el-button type="primary" @click="dialogFormVisible = false"
          >Confirm</el-button
        >
      </span>
    </el-dialog>
    <el-table
      :data="tableData"
      stripe
      style="width: 100%; border: 2px solid #dcdfe6"
    >
      <el-table-column prop="stt" label="STT" width="180"> </el-table-column>
      <el-table-column prop="name" label="Tên học sinh" width="180">
      </el-table-column>
      <el-table-column prop="brithday" label="Ngày sinh" width="180">
      </el-table-column>
      <el-table-column prop="classname" label="Tên lớp"> </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialogFormVisible: false,
          value1: '',
      form: {
        name: "",
        region: "",
        date1: "",
        date2: "",
        delivery: false,
        type: [],
        resource: "",
        desc: "",
      },
      tableData: [
        {
          stt: "1",
          name: "Nguyễn Văn Hoàng",
          brithday: "5/6/2004",
          classname: "Lớp 9A",
        },
        {
          stt: "2",
          name: "Đặng Văn Phú",
          brithday: "5/2/2004",
          classname: "Lớp 9B",
        },
        {
          stt: "3",
          name: "Trịnh Đình Thái",
          brithday: "3/2/2004",
          classname: "Lớp 9A",
        },
        {
          stt: "4",
          name: "Đỗ Văn Khởi",
          brithday: "12/8/2004",
          classname: "Lớp 9D",
        },
        {
          stt: "5",
          name: "Nguyễn Thái Phú",
          brithday: "8/1/2004",
          classname: "Lớp 9C",
        },
      ],
    };
  },
};
</script>

<style>
</style>