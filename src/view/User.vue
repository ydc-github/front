<template>
<div class="app-container">
  <div class="btn">
    <el-button type="primary" @click="dialogFormVisible = true">添加用户</el-button>
    <el-dialog title="添加用户" :visible.sync="dialogFormVisible">
      <el-form :model="form" ref="dialogformtest" >
        <el-form-item label="姓名" :label-width="formLabelWidth" prop="name">
          <el-input v-model="form.name" autocomplete="off" placeholder="请输入姓名" clearable></el-input>
        </el-form-item>
        <el-form-item label="地址" :label-width="formLabelWidth" prop="address">
          <el-input v-model="form.address" autocomplete="off" placeholder="请输入地址" clearable></el-input>
        </el-form-item>
        <el-form-item label="日期" :label-width="formLabelWidth" prop="date">
          <el-date-picker v-model="form.date" type="daterange" range-separator="-" start-placeholder="开始日期" end-placeholder="结束日期"></el-date-picker>
        </el-form-item>
        <el-form-item label="活动区域" :label-width="formLabelWidth" prop="region">
          <el-select v-model="form.region" placeholder="请选择活动区域">
            <el-option label="区域一" value="shanghai"></el-option>
            <el-option label="区域二" value="beijing"></el-option>
          </el-select>
        </el-form-item>
      </el-form>
      <div slot="footer" class="dialog-footer">
        <el-button type="primary" @click="dialogFormVisible = false">确定</el-button>
        <el-button @click="resetForm('dialogformtest')">重置</el-button>
        <el-button @click="dialogFormVisible = false">取消</el-button>
      </div>
    </el-dialog>
  </div>
  <el-table :data="tableData" stripe style="width: 100%">
    <el-table-column prop="date" label="日期" width="180">
    </el-table-column>
    <el-table-column prop="name" label="姓名" width="180">
    </el-table-column>
    <el-table-column prop="address" label="地址">
    </el-table-column>
  </el-table>
</div>
</template>

<script>
export default {
  data () {
    return {
      tableData: [{
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄'
      }, {
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }],
      dialogTableVisible: false,
      dialogFormVisible: false,
      form: {
        name: '',
        address: '',
        date: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      },
      formLabelWidth: '12%'
    }
  },
  components: {},
  methods: {
    resetForm (formName) {
      this.$refs[formName].resetFields()
    }
  }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.btn {
  text-align: left;
}
</style>
