# GetKeypointsTool

```python3
import copy

#given
annotated_data_dictionary = 1
dataset["images"]
dataset["annotations"]
dataset = 1
max_id = 1
# next_id = max_id+1

def find_route(data, annotated_image_id):
    return [image for image in data if image.get('file_name') == annotated_image_id][0]

def split_at(s, c, n):
    split_1 = s.split(c).join[:n]
    pslit_2 = s.split(c).join[n:]
    return split_1, split_2

for annotated_image_id in annotated_data_dictionary:
    for image in dataset["images"]:
        annotated_image = find_route(dataset["images"], annotated_image_id)
        annotated_image_file_name = split_at(annotated_image["file_name"], "_", -1)
        if image["last_modified"] == None and (annotated_image_file_name[0] and annotated_image_file_name[1]) in image["file_name"]:
            new_annotation_data = annotated_data_dictionary[annotated_image_id]
            new_annotation_data_copy = copy.deepcopy(new_annotation_data)
            count_annotation_data = 0
            for individual_annotation_data in new_annotation_data_copy:
                #1. Check the number of annotation data iterated for id:32
                count_annotation_data += 1
                print(f'#1: count_annotation_data: {count_annotation_data}')
                individual_annotation_data["id"] = max_id + 1 #! OR next_id
                individual_annotation_data["image_id"] = image["id"]
                keypoints = individual_annotation_data["keypoints"]
                #2-1. If count_annotation_data == 3, print out the keypoints of this third annotation_data
                if count_annotation_data == 3:
                    print(f'#2-1. The 3rd annotation_data: {keypoints} ')
                #2-2. !ONLY IF 2-1 DIDN'T WORK OUT!! 
                # Check which set of keypoints does not match the keypoints of id:32
                # = "Detect the third individual_annotation_data to see from which annotation data that extra keypoints comes from"
                print(f'#2-2. original_annotation_data: {keypoints}')
                for visiblity_index in range(0, len(keypoints), 3):
                    # if (keypoint_index+1)%3 == 0:
                    x = keypoints[visiblity_index-2]
                    y = keypoints[visiblity_index-1]
                    #3. check if the last visibility_index is 84
                    print(f'#3: visiblity_indes: {visiblity_index}')




            for i in new_annotation_data_copy["keypoints"]:



```
