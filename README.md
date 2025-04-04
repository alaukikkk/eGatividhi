# eGatividhi - Construction Progress Monitoring System

eGatividhi is an AI-powered construction progress monitoring system designed to help urban local bodies (ULBs) and state agencies assess construction status remotely. The system uses computer vision and machine learning to analyze construction site images and track project progress.

### Demo Video

https://github.com/user-attachments/assets/e23314b3-77b7-4bd7-a048-c71886b82db9





### Image Results Example

Result Image 1 
![Screenshot from 2025-02-12 08-29-12](https://github.com/user-attachments/assets/6e062a14-5d8c-4afe-bf14-eca24f07e6a0)

Result Image 2
![Screenshot from 2025-02-12 08-29-48](https://github.com/user-attachments/assets/fe0b70a6-8f12-4c8d-a22a-242bf82753f2)



## Features

### Image Analysis
- Automated construction stage identification
- Progress comparison between timeline snapshots
- Structural similarity analysis (SSIM)
- Visual difference detection and highlighting
- Percentage-based progress estimation

### Technical Capabilities
- Image alignment and registration
- Feature detection and matching using ORB
- Homography transformation
- Contour detection and analysis
- Change percentage calculation

### Web Interface
- User-friendly dashboard
- Image upload functionality
- Progress visualization
- Statistical reporting
- Responsive design using Bootstrap

## Technology Stack

- **Backend**
  - Python/Flask
  - OpenCV
  - NumPy
  - scikit-image
  - PIL (Python Imaging Library)

- **Frontend**
  - HTML5/CSS3
  - JavaScript
  - Bootstrap 5.3.3
  - Various libraries:
    - AOS (Animate On Scroll)
    - GLightbox
    - Isotope
    - Swiper
    - PureCounter

## Setup Instructions

1. Clone the repository:
```bash
git clone [repository-url]
cd egatividhi
```

2. Create and activate a virtual environment:
```bash
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required packages:
```bash
pip install flask opencv-python numpy pillow scikit-image requests
```

4. Create required directories:
```bash
mkdir uploads results
```

5. Run the application:
```bash
python app.py
```

The application will be available at `http://localhost:5000`

## Project Structure

```
egatividhi/
├── app.py                  # Main Flask application
├── assets/                 # Static assets
│   ├── css/
│   ├── js/
│   ├── scss/
│   └── vendor/            # Third-party libraries
├── templates/             # HTML templates
├── uploads/              # Image upload directory
└── results/              # Analysis results directory
```

## Usage

1. Navigate to the web interface
2. Upload two construction site images for comparison
3. The system will:
   - Align and compare the images
   - Calculate similarity scores
   - Generate progress estimates
   - Provide visual feedback of changes
   - Create detailed analysis reports

## API Endpoints

### POST /upload
Accepts two images and returns analysis results:
- SSIM score
- Change percentage
- Progress estimation
- Processed image with highlighted differences
- Construction stage description
- Construction level assessment

Response format:
```json
{
    "ssim_score": float,
    "change_percentage": float,
    "progress_estimation": float,
    "image": string (base64),
    "llava_description": string,
    "construction_level": string,
    "construction_stage": string
}
```

## Security Considerations

- Implements secure file upload handling
- Uses `secure_filename` for file storage
- Restricts allowed file extensions
- Validates input files before processing


## License

This project uses various third-party components with their respective licenses:
- Bootstrap template license: https://bootstrapmade.com/license/
- Other components maintain their original licenses