$# 利用Page类和limit方法分页

        $Wxch_indent = M("Wxch_indent"); // 实例化Wxch_indent对象
        $count = $Wxch_indent->where($where)->count();// 查询满足要求的总记录数
        $Page  = $this->Page($count, 15);// 实例化分页类 传入总记录数和每页显示的记录数(25)
        $show       = $Page->show();// 分页显示输出
        // 进行分页数据查询 注意limit方法的参数要使用Page类的属性
        $list  = $Wxch_indent->where('1')->order('id desc')->limit($Page->firstRow . ',' . $Page->listRows)->select();
        $this->assign('list',$list);// 赋值数据集
        $this->assign('Page',$show);// 赋值分页输出
        $this->display(":index"); // 输出模板

