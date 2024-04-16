# Smart-E-Voting-System-with-Biometric-Verification-for-Integrity-
1. Components Overview:
   - **Fingerprint Scanner**: The Adafruit_Fingerprint library is used to interface with the fingerprint scanner. It allows for fingerprint enrollment and verification.
   - **LCD Display**: The LiquidCrystal_I2C library is utilized to control the LCD display. It shows voting options (candidates A, B, C, D) and displays the winner at the end.
   - **Buttons (S1 to S5)**: These buttons are used for voter interaction. Each button corresponds to a candidate, and pressing a button casts a vote for that candidate.
2. Initialization and Setup:
   - The code begins with including necessary libraries and defining pin numbers for components.
   - Wire.begin() initializes communication for I2C devices like the LCD.
   - finger.begin(57600) initializes the fingerprint scanner at a baud rate of 57600.
   - lcd.init() and lcd.backlight() set up the LCD and turn on the backlight.
3. Fingerprint Enrollment:
   - Upon startup, the code prompts for fingerprint enrollment using Serial communication.
   - Voters are asked to place their finger on the scanner and enter an ID number for their fingerprint.
   - The enrollFingerprint() function handles the enrollment process, including image capture, conversion, and model creation.
   - The fingerprint data is stored with the associated ID for later verification during voting.
4. Voting Process:
   - The main loop continuously monitors the state of the push buttons (S1 to S5) for voter input.
   - When a button is pressed, the corresponding candidate's vote count increases.
   - Fingerprint verification is performed before each vote to ensure the voter's identity.
   - Once all votes are cast (triggered by pressing a separate button, S5), the winner is determined based on the highest vote count.
   - The LCD displays the winning candidate's name, or if there's a tie or no votes, it shows a relevant message.
5. Functions and Logic:
   - The checkFingerprint() function handles fingerprint verification during voting.
   - It prompts the voter to place their finger, verifies the fingerprint against stored data, and prevents multiple votes from the same person.
   - Other utility functions like readnumber() and getFingerprintEnroll() assist in user input and fingerprint processing.
