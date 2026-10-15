# OpenCV Document Scanner

This project takes a photo of a document taken at an angle and straightens it, so it looks like a flat, top-down scan. It uses Python and OpenCV.

## What's in the project

```
OpenCV-main/
├── pyimagesearch/
│   ├── image.png            # sample image
│   └── transform.py         # does the straightening
├── get_points.py            # click the 4 corners of the document
└── transform_example.py     # run this to straighten the image
```

## Setup

Install the two libraries you need:

```bash
python -m pip install opencv-python numpy
```

## How to use it

**Step 1: Get the corner points**

Run:

```bash
python get_points.py
```

Click the 4 corners of the document. The points are printed in the terminal, like this:

```
Clicked points: [(46, 152), (226, 75), (301, 165), (119, 279)]
```

To use your own image, change `image_path` inside `get_points.py`.

**Step 2: Straighten the image**

Run this, using your own points inside the quotes:

```bash
python transform_example.py -i pyimagesearch/image.png -c "[(46, 152), (226, 75), (301, 165), (119, 279)]"
```

Two windows open: **Original** and **Warped**. Press any key to close them.

## Common problems

| Problem | Fix |
|---------|-----|
| `No module named 'cv2'` | Run `python -m pip install opencv-python` |
| `arguments are required: -c/--coords` | Add the corner points with `-c` |
| The result looks wrong | Run `get_points.py` again and click the corners more carefully |

## Credits

Based on the four-point transform technique from [PyImageSearch](https://pyimagesearch.com/).
