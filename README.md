# Lane Detection

## About

This repository compares two methods to achieve higher accuracy for lane detection applications. The former is the conventional segmentation approach and the latter will tackle this problem in an end-to-end manner. The segmentation approach depends on the cross-entropy loss in order to learn the road markings by attention. However this approach is not necessarily the most accurate. Since the final line coordinates are desired, a complete end-to-end method should achieve better results.

This end-to-end architecture consist of two parts. The first part is an off the shelf network to predict weight maps. These weights are applied to a mesh grid which are used for the last step. The last step can be considered as the final layer of the network which solves a weighted system of equations to calculate the final curve parameters of the road markings. The amount of weight maps depends on the amount of lane lines the network ought to detect. This means that a direct regression can be performed to the desired curve coordinates. After all, backpropagation through the whole architecture is now possible.

Finally we show results for egolane detection. The implementation proofs that this direct optimization is indeed possible and can achieve better results than the conventional segmentation approach. Moreover, this module can be applied to a broad range of tasks since the first stage of the architecture can be chosen freely. The extention to other domains such as object detection is considered as future work which also shows the effectiveness of this architecture.

## Creator
GestureGaming Application is created by [Sunny Tripathi](https://github.com/sxnnytripathi/).

## Requirements

I just updated the code to the most recent version of Pytorch (=pytorch 1.1) with python 3.7.
The other required packages are: opencv, scikit-learn, torchvision, numpy, matplotlib, json/ujson and pillow.

![end_to_end](https://user-images.githubusercontent.com/9694230/51836593-12459400-2301-11e9-9d1b-37cbe936f8cc.gif)

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.


## License
Do What The Fuck You Want To Public License [(WTFPL)](http://www.wtfpl.net/about/) is a free software license.
