# face_recognition
The main code file is indentify.py
This code is a Python script that uses the face_recognition library to perform face recognition on a group photo
and identify known individuals from their known face images. It draws rectangles around the recognized faces and labels them with their names.
Here's a brief explanation of the code:

1. Import necessary libraries: The code imports the required libraries, including face_recognition for face recognition tasks,
PIL (Python Imaging Library) for image processing, and TensorFlow (though it seems not to be used in this script).

2. Load known face images and encode them: The script loads images of known individuals (Bill Gates, Steve Jobs, and Elon Musk)
from the './img/known/' directory, and then encodes their faces using the face_recognition.face_encodings() function.
The resulting face encodings are stored in separate arrays.

3. Define arrays of known face encodings and names: The script creates two arrays - one for storing the known face encodings (known_face_encodings)
and another for storing the corresponding names (known_face_names).

4. Load the test image and detect faces: The script loads the test image ('./img/groups/team2.jpg')
and uses the face_recognition.face_locations() function to find the locations of faces in the image.
It also encodes these detected faces using face_recognition.face_encodings().

5. Convert to PIL format and create ImageDraw instance: The detected test image is converted into the PIL format to enable drawing on it.
An ImageDraw instance is created to annotate the image.

6. Face recognition loop: The code iterates through each detected face in the test image and compares their encodings
with the known face encodings using face_recognition.compare_faces(). If a match is found, the person's
name is retrieved from known_face_names.

7. Draw rectangles and labels: For each recognized face, a rectangle is drawn around the face using the ImageDraw.rectangle() method.
A label is drawn at the bottom of the rectangle with the person's name using the ImageDraw.text() method.

8. Display and save the annotated image: The annotated test image is displayed using pil_image.show(),
and then it is saved as 'identify4.jpg' using pil_image.save('identify4.jpg').

Note: Before running the code, make sure you have the necessary libraries installed, and the paths to the known face images
and the test image are correct. Additionally, ensure that the known face images are accurately labeled and recognized faces are encoded correctly.
The accuracy of the face recognition process depends on the quality and representation of the known face images.
