### Leaderboard
![Kaggle leaderboard](https://imgur.com/5oHf9Al.png)
### Submissions
![Kaggle submit score](https://imgur.com/CSOfNT9.png)
### Detection
- Немного поигрался с U-net'ом
- Заменил на предобученный Mask R-CNN ResNet-50 FPN из torchvision.models.detection - дало сильный прирост
- Добавил аугментации Rotate/Blur/GaussianNoise - дало небольшой прирост
- Подобрал пороговое значение детекции
### Recognition
- Взял CRNN из семинара по OCR, обучал 1 эпоху, увеличил размер батча
- Разворачивал найденные детектором BBox'ы с помощью PerspectiveTransform - дало ощутимый прирост
- Перед обучением привёл все буквы в выборке к верхнему регистру латиницы - дало ощутимый прирост
- Обучался на данных до + после PerspectiveTransform (x2 выборка) - дало небольшой прирост
### Optimization
- Использовал Adam (lr=3e-4) с уменьшением LR на плато
- Пробовал [RAdam](https://github.com/LiyuanLucasLiu/RAdam) - прироста не дало
