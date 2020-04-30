# SSDAutoLabel
https://www.youtube.com/watch?v=hECRUHlTTqg

I had SSD - Mobilenet.

I needed more image dataset.

I had to take pictures and label them with a labeling program. It was so annoying. So I made an Auto Labeling code using ssd model that I had.

If you have your own ssd model, change it and apply it. 

python3 autolabel.py --modeldir=model --imagedir=images --failimagedir=fail --successdir=success

imagedir is images in folder failimagedir is folder that sended images that failed to detect drone successdir is folder that generated xml file

put your model in model folder

if you write 'space' key, then apear next picture. if you write 'd' key, then delete xml file and move strange image file to failfolder. so if you see not good label image, then enter 'd' key

and if your yolo can not find object that you want to detect, my code will print fail and auto move the picture to failfolder

eventually, you just label pictures that fail to be detected

1. classify detected pictures and not detected pictures
 python classify.py --modeldir=model --imagedir=images --failimagedir=fail --successdir=success
2.make sure
  python3 autolabel.py --modeldir=model --imagedir=images --failimagedir=fail --successdir=succes
저는 드론 ssd가 있었고 더 많은 이미지데이터셋을 원했습니다.

그래서 수백장의 드론 사진을 찍었는데 라벨링하는 것이 너무 귀찮아서

내가 가지고 있는 ssd mobilenet으로 라벨링을 하면 편하게 할수 있지 않을까 하여 작성해보았습니다.

처음에는 사진들 넣고 쫙 돌렸으나 디텍팅이 되지않은 사진들도 있고 이상한곳에 디텍팅한 사진들도 있어서 잘 라벨링을 하는지 모니터링하면서 진행해야했습니다.

따라서 만약에 라벨링이 잘되면 엔터를 눌러 다음 사진으로 넘어가세요. 자동으로 xml파일이 생성되어 있을겁니다.

엔터를 누른 후 나온 다음 사진이 라벨링이 안되어 있으면 xml파일을 생성하지 않고 fail되었다고 print가 되며 그 사진은 ‘실패폴더’로 이동합니다. 또 라벨링은 되어있는데 엉뚱한 곳을 라벨링하고 있으면 ‘d’ 키를 누르세요

d 키를 누르면 만들어진 xml파일이 삭제되고 그 사진은 ‘실패폴더’로 이동합니다.

결국 저는 탐지 못한 드론 사진만 라벨링하면 됩니다.
1. 먼저 classify.py로 드론이 감지되는 사진과 아닌 사진으로 나눕니다. 드론으로 감지안된 사진은 직접 라벨링해야합니다.
2. 드론으로 감지된 사진폴더를 autolabel.py로 실행하여 사진한장씩 불러와서 라벨링이 잘되었는지 보면서 진행합니다 라벨링이 잘안되어있으면 
d를 누르면 만들어진 xml파일도 삭제되고 성공폴더로 이동되어있던 사진도 돌아옵니다.

https://blog.naver.com/khw11044/221926134482
