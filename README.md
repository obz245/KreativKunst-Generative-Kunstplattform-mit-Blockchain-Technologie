# KreativKunst-Generative-Kunstplattform-mit-Blockchain-Technologie
KreativKunst ist eine dezentralisierte Plattform, die Künstlern ermöglicht, einzigartige, KI-generierte Kunstwerke zu schaffen, zu verkaufen und zu besitzen, unter Verwendung von NFTs und Smart Contracts.
# KreativKunst: Generative Kunstplattform mit Blockchain-Technologie

# Import necessary libraries
import random
import hashlib
import datetime

# Define the Artwork class
class Artwork:
    def __init__(self, artist, style, creation_date):
        self.artist = artist
        self.style = style
        self.creation_date = creation_date
        self.id = hashlib.sha256((artist + style + creation_date).encode()).hexdigest()

    def __str__(self):
        return f"Artwork ID: {self.id}\nArtist: {self.artist}\nStyle: {self.style}\nCreation Date: {self.creation_date}"

# Define the ArtworkGenerator class
class ArtworkGenerator:
    def __init__(self):
        self.styles = ["Abstract", "Surrealism", "Cubism", "Impressionism", "Expressionism"]

    def generate_artwork(self, artist):
        style = random.choice(self.styles)
        creation_date = datetime.datetime.now().strftime("%Y-%m-%d %H:%M:%S")
        return Artwork(artist, style, creation_date)

# Demo
if __name__ == "__main__":
    # Create an instance of ArtworkGenerator
    generator = ArtworkGenerator()

    # Generate a sample artwork
    artist_name = "John Doe"
    artwork = generator.generate_artwork(artist_name)

    # Display the generated artwork
    print("Generated Artwork:")
    print(artwork)
