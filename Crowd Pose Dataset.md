# Crowd Pose dataset
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
