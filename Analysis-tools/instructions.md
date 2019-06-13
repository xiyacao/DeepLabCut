command to do keypoint analysis:

import deeplabcut
deeplabcut.create_new_project('demo','xiya',['/home/xiya/ROAR/code/path_to_video.mp4'])
path_config = '/path_to_config_file/config.yaml'
deeplabcut.extract_frames(path_config, 'manual','kmeans') # 'automatic', 'uniform'
deeplabcut.label_frames(path_config)
deeplabcut.check_labels(path_config)
deeplabcut.create_training_dataset(path_config) 

# train NN
deeplabcut.train_network(path_config, shuffle=1, displayiter=10, saveiters=500)     
deeplabcut.evaluate_network(path_config, Shuffles=[1], plotting=True)  
video_path = ['/home/xiya/ROAR/code/path_to_video.mp4']   
deeplabcut.analyze_videos(path_config, video_path)
deeplabcut.create_labeled_video(path_config, video_path)   
deeplabcut.plot_trajectories(path_config, video_path)  
