# 利用Page类和limit方法分页

  $Wxch_indent = M("Wxch_indent"); // 实例化User对象
        $count = $Wxch_indent->where($where)->count();
        $Page  = $this->Page($count, 15);
        $list  = $Wxch_indent->where($where)->order('id desc')->limit($Page->firstRow . ',' . $Page->listRows)->select();

        $this->assign('Page', $Page->show());

