# Plant Disease Detection Using Deep Learning

This project aims to develop an automated system to detect and classify plant diseases from images of plant leaves using deep learning techniques.

## Features
- Accurate detection and classification of plant diseases.
- Easy-to-use web or mobile interface for uploading leaf images.
- Real-time notifications via Pushbullet for disease detection results.

## Installation

1. **Clone the repository:**
    ```bash
    git clone https://github.com/jenisha-sherin/plant-disease-detection.git
    cd plant-disease-detection
    ```

2. **Install the required dependencies:**
    ```bash
    pip install -r requirements.txt
    ```

3. **Download the dataset and model:**
    - Follow the instructions in the `data/` and `model/` directories to download the necessary files.

## Pushbullet Integration

This project includes a Pushbullet app to send real-time notifications about plant disease detection results.

### Setting Up Pushbullet

1. **Create a Pushbullet Account:**
    - Sign up at [Pushbullet](https://www.pushbullet.com/) and create an account.

2. **Create an Access Token:**
    - Go to our account settings and create an access token. This token will be used to send notifications from the app.

3. **Add our Access Token to the Project:**
    - Create a file named `.env` in the project root directory and add your Pushbullet access token:
      ```plaintext
      PUSHBULLET_API_KEY=your_pushbullet_access_token
      ```

4. **Integrate Pushbullet in our Code:**
    - Ensure the Pushbullet integration code is in your script. Here’s an example of how you might set it up in Python:
      ```python
      import os
      from pushbullet import Pushbullet

      # Load Pushbullet API key from .env file
      pb = Pushbullet(os.getenv('PUSHBULLET_API_KEY'))

      # Function to send notification
      def send_pushbullet_notification(title, body):
          pb.push_note(title, body)
      
      # Example usage
      send_pushbullet_notification("Plant Disease Detected", "A disease has been detected in the uploaded leaf image.")
      ```

## Usage

1. **Run the Application:**
    ```bash
    python app.py
    ```

2. **Upload an Image:**
    - Use the web or mobile interface to upload an image of a plant leaf.

3. **Receive Notifications:**
    - Upon detection of a disease, a notification will be sent to your Pushbullet account with the results

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

