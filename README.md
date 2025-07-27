# MP3TagExplorer
open-source jaudiotagger library to read metadata from MP3 files.
       
       
    import org.jaudiotagger.audio.AudioFile;
    import org.jaudiotagger.audio.AudioFileIO;
    import org.jaudiotagger.tag.Tag;

    import java.io.File;

    public class Mp3MetadataViewer {
    public static void main(String[] args) {
        try {
            File mp3File = new File("song.mp3"); // replace with your file
            AudioFile audioFile = AudioFileIO.read(mp3File);
            Tag tag = audioFile.getTag();

            System.out.println("🎵 MP3 Metadata:");
            System.out.println("Title: " + tag.getFirst("TIT2"));
            System.out.println("Artist: " + tag.getFirst("TPE1"));
            System.out.println("Album: " + tag.getFirst("TALB"));
            System.out.println("Year: " + tag.getFirst("TYER"));

            int duration = audioFile.getAudioHeader().getTrackLength();
            System.out.println("Duration: " + duration + " seconds");

        } catch (Exception e) {
            System.out.println("Error: " + e.getMessage());
        }
    }
}

