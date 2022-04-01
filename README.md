# mmd-motion-track-record
mmd motion track record
过程与 https://github.com/peterljq/OpenMMD 的流程一致，使用的工具完全相同，但是我的windows上由于未知原因无法运行openpose，所以我把第一步用colab实现
用colab生成人体关键点的json数据，如 copy_of_openmmd.ipynb 所示

我用的视频有三个人在跳舞，我想捕获的是处于c位的人物，所以我搜索了参数 max_people_number的用法，我将这个参数设为1，根据定义，在捕获的时候会将捕获到的人的可能性排序，取分数排在第一的来捕捉动作。这个参数的说明如下：

-number_people_max (This parameter will limit the maximum number of people
      detected, by keeping the people with top scores. The score is based in
      person area over the image, body part score, as well as joint score
      (between each pair of connected body parts). Useful if you know the exact
      number of people in the scene, so it can remove false positives (if all
      the people have been detected. However, it might also include false
      negatives by removing very small or highly occluded people. -1 will keep
      them all.) type: int32 default: -1

但是这样虽然在大多数情况下能捕获到c位人物的动作，但有时会跳跃到非
位上。于是我截取了舞蹈视频，把非c位的人截到只剩胳膊（看不到完整身体）
