# musicimport pygame
import time

# Initialize pygame
pygame.init()

# Set up the frequency and duration for the tone
frequency = 440  # Hz (A4 note)
duration = 2  # seconds

# Set up the audio format
pygame.mixer.init()
pygame.mixer.set_num_channels(1)  # Set the number of channels (1 for mono)

# Generate the tone
sound = pygame.mixer.Sound(pygame.mixer.Sound.buffer(pygame.mixer.Sound(\
    pygame.mixer.get_init()[0], pygame.mixer.AUDIO_S16SYS), \
    bytes([int(127.5 + 127.5 * math.sin(math.pi * x / (44100 / frequency))) for x in range(int(44100 * duration))] * 2)))

# Play the tone
sound.play()

# Wait for the tone to finish playing
time.sleep(duration)

# Quit pygame
pygame.quit()
