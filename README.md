# nbgui
embed a live interactive gui in jupyter notebooks

uses jupyter_rfb, pyglet, and imgui

- rendering:
  - gui is rendered in a hidden window
  - window pixels are placed into a numpy array
  - uses jupyter-rfb for streaming the remote framebuffer to the jupyter notebook in realtime
- ui events:
  - jupyter-rfb streams ui io events back to python
  - we translate the jupyter-rfb events + coordinates into the format `dear imgui` expects then notify it so it can handle them
- can use the entire `dear imgui` ecosystem for ui components + building the gui logic
- the widget is resizable by dragging the lower right corner

<img width="1363" alt="image" src="https://github.com/user-attachments/assets/66d84dd1-d532-44c0-9888-67cca04906ed">
