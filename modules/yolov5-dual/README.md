# 双模态yolo
## 1、数据集制作
        需要两个输入，比如可见光图像和红外图像，用同一个label，yaml文件如下
                  train: data/train.txt
                  train2: data/train2.txt
                  val: data/val.txt
                  val2: data/val2.txt
                  # Classes
                  nc: 1  # number of classes
                  names: ['uav']  # class names
## 2、训练
       python train.py --data data/dualuav.yaml --cfg models/attentionuav5.yaml --weights weights/yolov5s.pt --batch-size 16--epochs 100
## 3、测试
       python dualdetect.py  --source ./data/test_images --source2 ./data/test_images2 --conf 0.2 --weights ./weights/best.pt
