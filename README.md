# kaggle-open-image2019
centernet已经可以直接运行测试，按照centernet的README下载相应的预训练模型到centernet/models文件夹（https://github.com/xingyizhou/CenterNet）；按照网页链接的步骤来

在ctdet.py文件下show_results函数下修改结果的存储路径；

环境：RTX2080ti、Ubuntu18.04、pytorch1.1、cuda10.0

注意：如果使用的是pytorch1.x,因为1.x移除了ffi,则/src/models/DCNV2/src下的build.py和build_double.py文件需要修改

from torch.utils.ffi import create_extension替换为from torch.utils.cpp_extension import BuildExtension

ffi = create_extension替换为ffi = BuildExtension

在Cornernet目录下运行python demo.py ctdet --demo /path/to/image/or/folder/or/video --load_model ../models/ctdet_coco_dla_2x.pth
