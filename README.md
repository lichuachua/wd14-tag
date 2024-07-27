# Use Smiling Wolf's wd to add tag for image
# 参考：https://github.com/kohya-ss/sd-scripts
# 仅使用了kohya-ss/sd-scripts中的以下几个文件改造而来
- /fintune/tag_images_by_wd14_tagger
- /library
- /requirements.txt
- /setup.py

# 运行：
1. pip install --use-pep517 --upgrade -r requirements.txt   
【可能会报错"ERROR: No matching distribution found for bitsandbytes==0.43.0 "，改成推荐的版本即可】
2. cd finetune
3. python tag_images_by_wd14_tagger.py "../dataset" --batch_size=8 --model_dir="../tag_models/wd-v1-4-moat-tagger-v2" --remove_underscore --general_threshold=0.35 --character_threshold=0.35 --caption_extension=".txt" --max_data_loader_n_workers=2 --debug --undesired_tags=""
【可能会报错"UnboundLocalError: cannot access local variable 'torch' where it is not associated with a value"，在其对应位置上import torch即可】

# 生成
运行后新增了两个文件夹library包和下载的模型【library.egg-info/ 和 tag_models/】

