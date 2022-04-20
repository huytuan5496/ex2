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
      title="Thông tin lớp học thêm mới "
      :visible.sync="dialogFormVisible"
    >
      <el-form :model="form">
        <el-form-item label="Lớp học ">
          <el-input v-model="form.name" autocomplete="off"></el-input>
        </el-form-item>
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
      <el-table-column prop="stt" label="STT" width="350"> </el-table-column>
      <el-table-column prop="className" label="Tên lớp "> </el-table-column>
    </el-table>
  </div>
</template>

<script>
export default {
  data() {
    return {
      dialogFormVisible: false,
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
          className: "Lớp 9A",
        },
        {
          stt: "2",
          className: "Lớp 9B",
        },
        {
          stt: "3",
          className: "Lớp 9C",
        },
        {
          stt: "4",
          className: "Lớp 9D",
        },
      ],
    };
  },
};
</script>

<style>
</style>