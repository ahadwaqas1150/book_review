<template>
    <div>
      <h1>Book Categories</h1>
      <div v-for="(books, category) in booksDictionary" :key="category">
        <h2>{{ category }}</h2>
        <ul>
          <li v-for="(book, index) in books" :key="index">
            <h3>{{ book[0] }}</h3>
            <p><strong>Author:</strong> {{ book[1] }}</p>
            <p><strong>Description:</strong> {{ book[2] }}</p>
            <p><strong>Review:</strong> {{ book[3] }}</p>
            <img :src="book[4]" :alt="book[0]" style="width: 100px;">
          </li>
        </ul>
      </div>
    </div>
  </template>
  
  <script>
   console.log("Hello World")
  export default {
    
    data() {

      return {
       
        booksDictionary: {
          Fiction: [
            ["To Kill a Mockingbird", "Harper Lee", "A novel about the serious issues of rape and racial inequality told through the eyes of a young girl.",
            "Harper Lee's 'To Kill a Mockingbird' is a timeless classic that delves deep into the complexities of human morality and justice. The narrative, set in the American South during the 1930s, is poignantly conveyed through the innocent and perceptive eyes of Scout Finch, a young girl coming of age in a world marred by prejudice and social injustice. The novel's portrayal of her father, Atticus Finch, as a paragon of virtue and a beacon of hope in the face of overwhelming bigotry, is both inspiring and heart-wrenching. Lee's masterful storytelling and profound thematic explorations make this novel an essential read, offering a powerful commentary on the human condition that remains as relevant today as it was upon its publication.",
            "https://images-na.ssl-images-amazon.com/images/I/81Ox45U5vQL.jpg"],
            ["1984", "George Orwell", "A dystopian novel set in a totalitarian society ruled by Big Brother.",
            "George Orwell's '1984' is a harrowing depiction of a dystopian future where freedom is obliterated, and the truth is perpetually manipulated by a totalitarian regime. The novel's protagonist, Winston Smith, navigates a world of constant surveillance, mind control, and pervasive propaganda. Orwell's meticulous world-building and his incisive critique of authoritarianism create a chillingly plausible scenario that serves as a stark warning about the dangers of unchecked power. The narrative is both gripping and deeply unsettling, leaving readers to ponder the fragile nature of truth and the extent to which individual autonomy can be suppressed in the name of state control.",
            "https://images-na.ssl-images-amazon.com/images/I/71kxa1-0wfL.jpg"]
          ],
          NonFiction: [
            ["Sapiens: A Brief History of Humankind", "Yuval Noah Harari", "A book that explores the history of the human species from the emergence of Homo sapiens to the present.",
            "Yuval Noah Harari's 'Sapiens: A Brief History of Humankind' is a remarkable exploration of the history of our species, tracing the journey from the cognitive revolution to the present day. Harari's ability to synthesize vast amounts of information into a coherent and engaging narrative is truly impressive. He challenges readers to reconsider many of their assumptions about human nature, society, and progress. The book is not only informative but also thought-provoking, as it delves into the profound impact of cultural, agricultural, and scientific revolutions on human life and the world around us. Harari's insightful analysis and compelling storytelling make 'Sapiens' a must-read for anyone interested in understanding the broader context of human history.",
            "https://images-na.ssl-images-amazon.com/images/I/713jIoMO3UL.jpg"],
            ["Educated", "Tara Westover", "A memoir about a young girl who, kept out of school, leaves her survivalist family and goes on to earn a PhD from Cambridge University.",
            "Tara Westover's memoir 'Educated' is an extraordinary account of one woman's quest for knowledge and self-discovery against the odds. Raised in a strict and abusive household in rural Idaho, Westover's early life was dominated by her father's extreme beliefs and her mother's alternative medicine practices. Deprived of formal education and subjected to severe physical and emotional abuse, Westover's journey to academia is nothing short of miraculous. Her eventual escape from her oppressive environment and her determination to educate herself, culminating in a PhD from Cambridge University, is both inspiring and heartbreaking. 'Educated' is a powerful testament to the transformative power of education and the resilience of the human spirit, offering a raw and honest look at the struggle for self-identity and the cost of breaking away from one's past.",
            "https://images-na.ssl-images-amazon.com/images/I/81WojUxbbFL.jpg"]
          ],
          ScienceFiction: [
            ["Dune", "Frank Herbert", "Set in a distant future amidst a huge interstellar empire, it tells the story of young Paul Atreides whose family accepts the stewardship of the desert planet Arrakis.",
            "Frank Herbert's 'Dune' is a monumental work in science fiction literature, renowned for its intricate world-building, complex characters, and profound philosophical themes. The story follows Paul Atreides, a young nobleman whose family takes control of Arrakis, the most valuable planet in the universe due to its exclusive supply of the spice melange. Herbert masterfully weaves a narrative that explores themes of power, religion, and ecology, set against the backdrop of a richly detailed universe. The novel's exploration of the human condition and its commentary on the cyclical nature of history and politics make it a thought-provoking read. 'Dune' is not just a tale of adventure and conflict; it's a profound meditation on the interplay between destiny and free will, and the consequences of human ambition.",
            "https://images-na.ssl-images-amazon.com/images/I/91b0C2YNSrL.jpg"]
          ],
          Fantasy: [
            ["The Hobbit", "J.R.R. Tolkien", "The prelude to the Lord of the Rings, following the journey of Bilbo Baggins as he embarks on an adventure with dwarves to reclaim their homeland.",
            "J.R.R. Tolkien's 'The Hobbit' is a charming and enchanting adventure that transports readers to the magical world of Middle-earth. The story follows Bilbo Baggins, a hobbit who reluctantly leaves his peaceful home to join a group of dwarves on a quest to reclaim their homeland from the dragon Smaug. Tolkien's masterful storytelling and rich imagination bring to life a world filled with wondrous creatures, epic battles, and timeless themes of courage, friendship, and personal growth. Bilbo's transformation from a timid and reluctant hero to a brave and resourceful adventurer is both heartwarming and inspiring. 'The Hobbit' is a delightful prelude to the more epic and complex 'Lord of the Rings' trilogy, but stands on its own as a beloved classic of fantasy literature.",
            "https://images-na.ssl-images-amazon.com/images/I/91b0C2YNSrL.jpg"]
          ],
          Mystery: [
            ["The Girl with the Dragon Tattoo", "Stieg Larsson", "A mystery novel about a journalist and a hacker who investigate the disappearance of a wealthy man's niece.",
            "Stieg Larsson's 'The Girl with the Dragon Tattoo' is a gripping and intricately plotted mystery that keeps readers on the edge of their seats. The novel introduces readers to Mikael Blomkvist, a disgraced journalist, and Lisbeth Salander, a brilliant but troubled hacker, as they team up to solve the decades-old disappearance of a wealthy industrialist's niece. Larsson's skillful weaving of complex characters, dark secrets, and unexpected twists creates a narrative that is both suspenseful and deeply engaging. The novel delves into themes of corruption, abuse, and redemption, painting a stark picture of societal dysfunction while celebrating the resilience and resourcefulness of its protagonists. 'The Girl with the Dragon Tattoo' is a compelling start to the Millennium Trilogy, offering a dark, thrilling, and thought-provoking read.",
            "https://images-na.ssl-images-amazon.com/images/I/81EVdQKxwLL.jpg"]
          ],
          HistoricalFiction: [
            ["The Book Thief", "Markus Zusak", "A story set in Nazi Germany, narrated by Death, about a young girl who finds solace in stealing books and sharing them with others.",
            "Markus Zusak's 'The Book Thief' is a poignant and heart-wrenching tale set against the grim backdrop of Nazi Germany. Narrated by Death, the novel follows young Liesel Meminger, who finds solace in stealing books and sharing them with her neighbors during the horrors of World War II. Zusak's lyrical prose and unique narrative perspective offer a deeply moving and original exploration of the human spirit's resilience in the face of unimaginable suffering. The relationships Liesel forms with her foster parents, her friends, and the Jewish man hiding in her basement are beautifully rendered, highlighting the power of words and stories to provide comfort and hope. 'The Book Thief' is a profound and unforgettable story of love, loss, and the enduring power of literature.",
            "https://images-na.ssl-images-amazon.com/images/I/81eB+7+CkUL.jpg"]
          ],
          Biography: [
            ["Steve Jobs", "Walter Isaacson", "A comprehensive biography of Steve Jobs, the co-founder of Apple Inc., based on over forty interviews with Jobs and hundreds of interviews with family, friends, and colleagues.",
            "Walter Isaacson's biography 'Steve Jobs' offers a comprehensive and intimate portrait of one of the most influential figures in modern technology. Based on extensive interviews with Jobs himself, as well as insights from family, friends, and colleagues, the book delves into the complexities of Jobs' personality, his relentless drive for perfection, and his vision for revolutionizing technology. Isaacson's balanced narrative captures Jobs' genius and his flaws, providing a nuanced view of the man behind the iconic Apple brand. The biography not only traces Jobs' professional achievements and challenges but also explores his personal life and the philosophical principles that guided his work. 'Steve Jobs' is a compelling read for anyone interested in understanding the mind of a visionary who reshaped the tech industry.",
            "https://images-na.ssl-images-amazon.com/images/I/71GRK4M1K7L.jpg"]
          ],
          Romance: [
            ["Pride and Prejudice", "Jane Austen", "A classic novel that explores the themes of love and social standing through the relationship between Elizabeth Bennet and Mr. Darcy.",
            "Jane Austen's 'Pride and Prejudice' is a timeless romance that deftly explores themes of love, social class, and the importance of personal integrity. The novel follows the spirited Elizabeth Bennet as she navigates the complexities of 19th-century English society and her evolving relationship with the proud and enigmatic Mr. Darcy. Austen's sharp wit and keen social commentary are evident throughout the story, making it as entertaining as it is insightful. The dynamic between Elizabeth and Darcy, marked by initial misunderstandings and gradual mutual respect, is beautifully portrayed and has captivated readers for generations. 'Pride and Prejudice' remains a beloved classic, offering a rich and satisfying exploration of the transformative power of love and the enduring value of personal growth.",
            "https://images-na.ssl-images-amazon.com/images/I/81af+MCATTL.jpg"]
          ]
        }
      }
    }
  }
  </script>

  