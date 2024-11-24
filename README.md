# nbgui
embed a live interactive gui in jupyter notebooks

uses jupyter_rfb, pyglet, and imgui

- rendering:
  - gui is rendered in a hidden window
  - window pixels are placed into a numpy array as a remote framebuffer
  - jupyter-rfb streams the remote framebuffer to the browser's jupyter notebook session in realtime
- ui events:
  - user does some io with the jupyter-rfb widget
  - jupyter-rfb signals the widget io events back to the python script
  - we translate the jupyter-rfb events + coordinates back into a compatible format and then pass them forward to `dear imgui`
- can use the entire `dear imgui` ecosystem for ui components + building the gui logic
- the widget is resizable by dragging the lower right corner

<img width="1363" alt="image" src="https://github.com/user-attachments/assets/66d84dd1-d532-44c0-9888-67cca04906ed">
