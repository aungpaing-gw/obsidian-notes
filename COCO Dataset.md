# COCO dataset

| Dataset    | Filename  | Numbers of files |
| ---------- | --------- | ---------------- | 
| Train      | train2017 | 115k             | 
| Validation | val2017   | 5k               |  
| Test       | test-dev  | 20k              | 


## Annotation format

### Object Detection
```python
annotations.json

	| -- "info" : Dict = {'year', 'version', 'descriptions', 'contributor'}
	
	| -- "licenses" : List[Dict] = {'url', 'name'}
	
	| -- "categories" : List[Dict]
				{id            : Int , 
				 name          : Str, 
				 supercategory : Str }
	
	| -- "images" : List[Dict]
				{id            :  Int, 
				 license       :  Int, 
				 file_name     :  Str,
				 height        :  Int, 
				 width         :  Int, 
				 data_captured :  Str }
	
	| -- "annotations" : List[Dict]
				{id            :  Int, 
				 image_id      :  Int,
				 category_id   :  Int, 
				 bbox          :  List[FLoat] : xywh, 
				 area          :  Int, 
				 segmentation  :  List[Float], 
				 iscrowd       :  Bool }

```

### Keypoint annoation
```python
annotations.json

	| -- "info" : Dict = {'year', 'version', 'descriptions', 'contributor'}
	
	| -- "licenses" : List[Dict] = {'url', 'name'}
	
	| -- "categories" : List[Dict]
				{id            : 1 , 
				 name          : person, 
				 keypoints     : ['nose', 'left_eye', 'right_eye', 'left_ear', 'right_ear', 'left_shoulder', 'right_shoulder', 'left_elbow', 'right_elbow', 'left_wrist', 'right_wrist', 'left_hip', 'right_hip', 'left_knee', 'right_knee', 'left_ankle', 'right_ankle'],
				 skeleton      : [[16, 14], [14, 12], [17, 15], [15, 13], [12, 13], [6, 12], [7, 13], [6, 7], [6, 8], [7, 9], [8, 10], [9, 11], [2, 3], [1, 2], [1, 3], [2, 4], [3, 5], [4, 6], [5, 7]]}
	
	| -- "images" : List[Dict]
				{id            :  Int, 
				 license       :  Int, 
				 file_name     :  Str,
				 height        :  Int, 
				 width         :  Int, 
				 data_captured :  Str }
	
	| -- "annotations" : List[Dict]
				{segmentation  :  List[Float],
				 num_keypoints :  Int,
				 area          :  Float, 
				 iscrowd       :  Bool,
				 keypoints     :  List[Int],
				 image_id      :  Int,
				 bbox          :  List[FLoat] : xywh, 
				 category_id   :  1, 
				 id            :  Int}
```


