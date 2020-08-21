# Render-SMPL-X-mesh-on-system-without-GPU

This repository acts as a workaround solution for the problem of overlaying [SMPL-X](https://github.com/vchoutas/smplify-x) mesh on an RGB image without having a GPU. 

As mentioned in this [issue](https://github.com/vchoutas/smplify-x/issues/47), SMPL-X mesh overlay can't be done on a browserless server. I have tweaked the code of visualizing from [here](https://github.com/vchoutas/smplify-x/blob/d0d096f6a1edb85ddc398a8d4e2005dc3b7f19ff/smplifyx/fit_single_frame.py#L509) 

1) To run this code, install SMPL-X following the steps as mentioned in the main github [repo](https://github.com/vchoutas/smplify-x).

2) Your directory will look like this:
```
smplify-x
│___README.md
│___LICENSE       
│   ...
│   
└
folder2
|_file1.txt
*Place_Jupyter notebook_here*
```

3) Change line 
    >out_mesh = trimesh.load_mesh("output_folder_check/meshes/S001C002P002R002A043_rgb_frame_1/000.obj") 
    
    to the path where the  trimesh **.obj** is stored. 
    
4) Change line
    >img = cv2.imread("data_folder_check/images/S001C002P002R002A043_rgb_frame_1.jpg")
    
    to the path where the corresponding image that has to be overlayed is stored.
    
5) Change line
    >out_img_fn = "overlay.png"
    
    to the path where you want to store the mesh-overlayed image.

