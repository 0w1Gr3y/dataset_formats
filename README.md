# dataset_formats
A description of common dataset formats
# COCO
COCO: COCO has five annotation types: for object detection, keypoint detection, stuff segmentation, panoptic segmentation, and image captioning. The annotations are stored using JSON.
```
annotation{
"id" : int,
"image_id": int,
"category_id": int,
"segmentation": RLE or [polygon],
"area": float,
"bbox": [x,y,width,height],
"iscrowd": 0 or 1,
}
categories[{
"id": int,
"name": str,
"supercategory": str,
}]
```
# Pascal VOC
Pascal VOC stores annotation in XML file. Below is an example of Pascal VOC annotation file for object detection.
```
<annotation> 
  <folder>Train</folder> 
  <filename>01.png</filename>      
  <path>/path/Train/01.png</path> 
  <source>  
    <database>Unknown</database> 
  </source>
  <size>  
    <width>224</width>  
    <height>224</height>  
    <depth>3</depth>   
  </size> 
  <segmented>0</segmented> 
  <object>  
    <name>36</name>  
    <pose>Frontal</pose>  
    <truncated>0</truncated>  
    <difficult>0</difficult>  
    <occluded>0</occluded>  
    <bndbox>   
      <xmin>90</xmin>   
      <xmax>190</xmax>   
      <ymin>54</ymin>   
      <ymax>70</ymax>  
    </bndbox> 
  </object>
</annotation>
```
# YOLO
```
.
├── train 
│     ├──images
│     │     └──<image_name>.jpg
│     └──labels
│           └──<image_name>.txt
│                    └──<object-class (starts from 0)> <x> <y> <width> <height>
├── valid              
│     ├──images
│     │    └──<image_name>.jpg
│     └──labels
│          └──<image_name>.txt
├── <dataset_name>.yaml
          train: ..</path/to/dataset/>train/images
          val: ..</path/to/dataset/>valid/images
          nc: 6
          names: ['cat1', 'cat2', 'cat3', 'cat4', 'cat5', 'cat6']
```
