<template>
<v-card class="mx-auto" color="grey-lighten-3" max-width="100vw">
    <v-layout>
      <v-app-bar
        color="teal-darken-4"
        display="fixed"
        image="https://www.shutterstock.com/image-vector/enchanting-anime-landscape-mistcovered-mountain-600nw-2301778699.jpg"
      >
        <template v-slot:image>
          <v-img
            gradient="to top right, rgba(19,84,122,.8), rgba(128,208,199,.8)"
          ></v-img>
        </template>

        <template v-slot:prepend>
          <v-app-bar-nav-icon></v-app-bar-nav-icon>
        </template>

        <v-app-bar-title>Book Review</v-app-bar-title>

        <v-spacer></v-spacer>

        <v-btn icon>
          <v-icon>mdi-magnify</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-heart</v-icon>
        </v-btn>

        <v-btn icon>
          <v-icon>mdi-dots-vertical</v-icon>
        </v-btn>
      </v-app-bar>

      <v-main>
        <v-container fluid>
          <div v-for="(books, category) in booksDictionary" :key="category">
            <h1>{{ category }}</h1>
            <v-row dense>
              <div class="flow">
                <card v-for="book in books" :key="book[0]" :title="book[0]" :author="book[1]" :description="book[2]" :summary="book[3]" :image="book[4]" :rating="book[5]" cols="12"></card>
              </div>
            </v-row>
          </div>
          
        </v-container>
        
      </v-main>
    </v-layout>
  </v-card>
  
  </template>

<script>
import { ref } from 'vue';
import card from '@/components/card.vue';


export default {
  components: { card },
  setup() {
    let age = 18
    const booksDictionary = {
    Fiction: [
        ["To Kill a Mockingbird", "Harper Lee", "A novel about the serious issues of rape and racial inequality told through the eyes of a young girl.",
        "Harper Lee's 'To Kill a Mockingbird' is a timeless classic that delves deep into the complexities of human morality and justice. The narrative, set in the American South during the 1930s, is poignantly conveyed through the innocent and perceptive eyes of Scout Finch, a young girl coming of age in a world marred by prejudice and social injustice. The novel's portrayal of her father, Atticus Finch, as a paragon of virtue and a beacon of hope in the face of overwhelming bigotry, is both inspiring and heart-wrenching. Lee's masterful storytelling and profound thematic explorations make this novel an essential read, offering a powerful commentary on the human condition that remains as relevant today as it was upon its publication.",
        "https://images-na.ssl-images-amazon.com/images/I/81Ox45U5vQL.jpg",2],
        ["1984", "George Orwell", "A dystopian novel set in a totalitarian society ruled by Big Brother.",
        "George Orwell's '1984' is a harrowing depiction of a dystopian future where freedom is obliterated, and the truth is perpetually manipulated by a totalitarian regime. The novel's protagonist, Winston Smith, navigates a world of constant surveillance, mind control, and pervasive propaganda. Orwell's meticulous world-building and his incisive critique of authoritarianism create a chillingly plausible scenario that serves as a stark warning about the dangers of unchecked power. The narrative is both gripping and deeply unsettling, leaving readers to ponder the fragile nature of truth and the extent to which individual autonomy can be suppressed in the name of state control.",
        "https://images-na.ssl-images-amazon.com/images/I/71kxa1-0wfL.jpg",4],
        ["The Great Gatsby", "F. Scott Fitzgerald", "A novel about the American dream and the downfall of those who attempt to reach its illusory goals.",
        "F. Scott Fitzgerald's 'The Great Gatsby' is a masterful critique of the American dream, set against the backdrop of the Roaring Twenties. Through the eyes of the narrator, Nick Carraway, we are introduced to Jay Gatsby, a mysterious and wealthy man whose life is a quest for the love of the elusive Daisy Buchanan. Fitzgerald's vivid portrayal of the Jazz Age and his exploration of themes such as greed, ambition, and the pursuit of happiness are timeless. The novel's tragic ending serves as a poignant reminder of the dangers of idealizing the past and the emptiness of materialism.",
        "https://images-na.ssl-images-amazon.com/images/I/71VZSv4XUnL.jpg",3],
        ["The Catcher in the Rye", "J.D. Salinger", "A novel about teenage rebellion and angst, as told by the iconic character Holden Caulfield.",
        "J.D. Salinger's 'The Catcher in the Rye' is a quintessential novel of teenage angst and rebellion. The story is narrated by Holden Caulfield, a disenchanted and troubled teenager who has been expelled from his prep school. As he wanders New York City, Holden grapples with the phoniness of the adult world, his deep sense of alienation, and the lingering grief over his brother's death. Salinger's portrayal of Holden's voice is raw, authentic, and unforgettable, capturing the complexity of adolescence in a way that resonates with readers of all ages. The novel's exploration of identity, loss, and the challenges of growing up makes it a timeless classic.",
        "https://images-na.ssl-images-amazon.com/images/I/81OthjkJBuL.jpg",2],
        ["Beloved", "Toni Morrison", "A haunting tale of slavery, motherhood, and the supernatural, centered on Sethe, an escaped slave haunted by her past.",
        "Toni Morrison's 'Beloved' is a powerful and haunting exploration of the legacy of slavery and its impact on individuals and families. The novel follows Sethe, an escaped slave who is haunted by the ghost of her dead daughter, Beloved. Morrison's lyrical prose and deeply moving narrative delve into themes of trauma, memory, and redemption. The novel's complex characters and rich symbolism create a profound and unforgettable reading experience. 'Beloved' is a testament to the enduring strength of the human spirit and the necessity of confronting and remembering the past to move forward.",
        "https://images-na.ssl-images-amazon.com/images/I/81TRW60ZhDL.jpg",3],
        ["Brave New World", "Aldous Huxley", "A dystopian novel exploring a future society where humanity is controlled through technology and conditioning.",
        "Aldous Huxley's 'Brave New World' presents a chilling vision of a future society where individuality and freedom are sacrificed for stability and happiness. In this dystopian world, humans are engineered and conditioned to fit into predetermined roles, and the use of a drug called soma ensures constant contentment. The novel's protagonist, Bernard Marx, begins to question the value of this seemingly perfect society. Huxley's incisive critique of consumerism, technology, and totalitarianism remains relevant, offering a stark warning about the potential consequences of sacrificing human dignity for the sake of progress.",
        "https://images-na.ssl-images-amazon.com/images/I/81ayUsETeML.jpg",2]
    ],
    NonFiction: [
        ["Sapiens: A Brief History of Humankind", "Yuval Noah Harari", "A book that explores the history of the human species from the emergence of Homo sapiens to the present.",
        "Yuval Noah Harari's 'Sapiens: A Brief History of Humankind' is a remarkable exploration of the history of our species, tracing the journey from the cognitive revolution to the present day. Harari's ability to synthesize vast amounts of information into a coherent and engaging narrative is truly impressive. He challenges readers to reconsider many of their assumptions about human nature, society, and progress. The book is not only informative but also thought-provoking, as it delves into the profound impact of cultural, agricultural, and scientific revolutions on human life and the world around us. Harari's insightful analysis and compelling storytelling make 'Sapiens' a must-read for anyone interested in understanding the broader context of human history.",
        "https://images-na.ssl-images-amazon.com/images/I/713jIoMO3UL.jpg",5],
        ["Educated", "Tara Westover", "A memoir about a young girl who, kept out of school, leaves her survivalist family and goes on to earn a PhD from Cambridge University.",
        "Tara Westover's memoir 'Educated' is an extraordinary account of one woman's quest for knowledge and self-discovery against the odds. Raised in a strict and abusive household in rural Idaho, Westover's early life was dominated by her father's extreme beliefs and her mother's alternative medicine practices. Deprived of formal education and subjected to severe physical and emotional abuse, Westover's journey to academia is nothing short of miraculous. Her eventual escape from her oppressive environment and her determination to educate herself, culminating in a PhD from Cambridge University, is both inspiring and heartbreaking. 'Educated' is a powerful testament to the transformative power of education and the resilience of the human spirit, offering a raw and honest look at the struggle for self-identity and the cost of breaking away from one's past.",
        "https://images-na.ssl-images-amazon.com/images/I/81WojUxbbFL.jpg",3],
        ["The Immortal Life of Henrietta Lacks", "Rebecca Skloot", "A non-fiction book detailing the story of Henrietta Lacks and the immortal cell line, HeLa, derived from her cancer cells in 1951.",
        "Rebecca Skloot's 'The Immortal Life of Henrietta Lacks' is a compelling narrative that interweaves the life story of Henrietta Lacks, a poor African-American woman whose cancer cells were taken without her knowledge, with the scientific breakthroughs made possible by her immortal cell line, HeLa. Skloot meticulously documents the impact of these cells on modern medicine, while also exploring the ethical, racial, and social issues surrounding their use. The book is a poignant tribute to Henrietta and her family, highlighting their struggle for recognition and justice. 'The Immortal Life of Henrietta Lacks' is a fascinating and thought-provoking read that raises important questions about ethics, consent, and the human cost of scientific progress.",
        "https://images-na.ssl-images-amazon.com/images/I/81wNJZflFbL.jpg",4],
        ["Becoming", "Michelle Obama", "A memoir by the former First Lady of the United States, chronicling her life from childhood to her years in the White House.",
        "Michelle Obama's 'Becoming' is an inspiring and intimate memoir that offers a candid and insightful look into the life of the former First Lady of the United States. Obama shares her journey from her childhood on the South Side of Chicago to her years as an executive and her role as First Lady. Through her personal anecdotes and reflections, she explores themes of identity, resilience, and the pursuit of one's dreams. The memoir is not only a testament to her own strength and determination but also a call to action for readers to find their voice and make a difference in the world. 'Becoming' is a powerful and uplifting story of self-discovery and empowerment.",
        "https://images-na.ssl-images-amazon.com/images/I/81h2gWPTYJL.jpg",3],
        ["The Wright Brothers", "David McCullough", "A biography of the Wright brothers, who invented and built the world's first successful airplane.",
        "David McCullough's 'The Wright Brothers' is a captivating biography that tells the incredible story of Wilbur and Orville Wright, the pioneers of aviation. McCullough delves into their early lives, their relentless pursuit of flight, and the many challenges they faced along the way. Through meticulous research and vivid storytelling, he brings to life the determination, ingenuity, and perseverance of the Wright brothers. The book not only chronicles their technical achievements but also highlights their character and the supportive family dynamics that played a crucial role in their success. 'The Wright Brothers' is an inspiring and engaging read that celebrates the spirit of innovation and the power of persistence.",
        "https://images-na.ssl-images-amazon.com/images/I/81PvkNo9pzL.jpg",2],
        ["Thinking, Fast and Slow", "Daniel Kahneman", "A book that explores the two systems of thinking that drive the way we make decisions.",
        "Daniel Kahneman's 'Thinking, Fast and Slow' offers a groundbreaking exploration of the cognitive processes that shape our decisions. Kahneman, a Nobel laureate in Economics, introduces readers to two systems of thinking: the fast, intuitive, and emotional System 1, and the slow, deliberate, and logical System 2. Through a wealth of research and real-world examples, he reveals how these systems interact and how they can lead to both brilliant insights and costly mistakes. The book provides valuable insights into the biases and heuristics that influence our judgment, offering practical advice on how to make better decisions. 'Thinking, Fast and Slow' is a must-read for anyone interested in understanding the complexities of the human mind.",
        "https://images-na.ssl-images-amazon.com/images/I/81QpkIctqPL.jpg",4]
    ],
    ScienceFiction: [
        ["Dune", "Frank Herbert", "Set in a distant future amidst a huge interstellar empire, it tells the story of young Paul Atreides whose family accepts the stewardship of the desert planet Arrakis.",
        "Frank Herbert's 'Dune' is a monumental work in science fiction literature, renowned for its intricate world-building, complex characters, and profound philosophical themes. The story follows Paul Atreides, a young nobleman whose family takes control of Arrakis, the most valuable planet in the universe due to its exclusive supply of the spice melange. Herbert masterfully weaves a narrative that explores themes of power, religion, and ecology, set against the backdrop of a richly detailed universe. The novel's exploration of the human condition and its commentary on the cyclical nature of history and politics make it a thought-provoking read. 'Dune' is not just a tale of adventure and conflict; it's a profound meditation on the interplay between destiny and free will, and the consequences of human ambition.",
        "https://images-na.ssl-images-amazon.com/images/I/91b0C2YNSrL.jpg",2],
        ["Neuromancer", "William Gibson", "A seminal cyberpunk novel that follows a washed-up computer hacker hired for one last job: to pull off the ultimate hack.",
        "William Gibson's 'Neuromancer' is a groundbreaking work in the cyberpunk genre, renowned for its visionary depiction of a dystopian future dominated by advanced technology and cyberspace. The novel follows Case, a washed-up computer hacker who is hired by a mysterious employer for one last job: to hack into the most secure systems in cyberspace. Gibson's vivid and gritty portrayal of a world where human consciousness can be uploaded and manipulated in digital realms has had a profound influence on the science fiction genre. 'Neuromancer' explores themes of identity, artificial intelligence, and the merging of humanity with technology, making it a thought-provoking and exhilarating read.",
        "https://images-na.ssl-images-amazon.com/images/I/81he+5cUEkL.jpg",4],
        ["Snow Crash", "Neal Stephenson", "A fast-paced cyberpunk novel set in a future America, where a computer virus threatens the world's virtual reality network.",
        "Neal Stephenson's 'Snow Crash' is a fast-paced and wildly imaginative cyberpunk novel that takes readers on a thrilling journey through a future America dominated by corporate franchises and virtual reality. The story follows Hiro Protagonist, a hacker and pizza delivery driver, as he uncovers a deadly computer virus that threatens to destroy both the real and virtual worlds. Stephenson's inventive world-building and sharp social commentary create a narrative that is both entertaining and thought-provoking. 'Snow Crash' is a masterful blend of action, satire, and cutting-edge technology, making it a must-read for fans of the genre.",
        "https://images-na.ssl-images-amazon.com/images/I/91+K4XglpPL.jpg",3],
        ["The Left Hand of Darkness", "Ursula K. Le Guin", "A science fiction novel exploring themes of gender and sexuality on a distant planet where inhabitants can change their sex.",
        "Ursula K. Le Guin's 'The Left Hand of Darkness' is a thought-provoking exploration of gender, sexuality, and society set on the distant planet of Gethen. The novel follows Genly Ai, an envoy from Earth, as he navigates the complex cultural and political landscape of Gethen, where inhabitants can change their sex at will. Le Guin's masterful storytelling and deep philosophical insights create a rich and immersive narrative that challenges readers to reconsider their own assumptions about gender and identity. 'The Left Hand of Darkness' is a landmark work in science fiction, offering a profound and timeless exploration of human nature and the possibilities of different social structures.",
        "https://images-na.ssl-images-amazon.com/images/I/81X4gP0AQJL.jpg",3],
        ["Foundation", "Isaac Asimov", "A science fiction series about the fall and rise of a galactic empire, based on the principles of psychohistory.",
        "Isaac Asimov's 'Foundation' series is a monumental work in science fiction, chronicling the fall and rise of a galactic empire through the lens of psychohistory—a fictional science that combines history, sociology, and statistical mathematics to predict the future. The series begins with the establishment of the Foundation, a group of scientists and scholars tasked with preserving knowledge and guiding humanity through a period of chaos. Asimov's intricate plotting, imaginative world-building, and exploration of themes such as power, knowledge, and destiny make the 'Foundation' series a seminal work in the genre. It offers a compelling vision of the future that continues to captivate readers.",
        "https://images-na.ssl-images-amazon.com/images/I/81RBKoN9FkL.jpg",5],
        ["The Martian", "Andy Weir", "A science fiction novel about an astronaut stranded on Mars, struggling to survive and communicate with Earth.",
        "Andy Weir's 'The Martian' is a gripping and scientifically detailed tale of survival set on Mars. The novel follows astronaut Mark Watney, who is stranded on the Red Planet after a mission goes awry. Using his ingenuity, engineering skills, and a good dose of humor, Watney battles the harsh Martian environment in a bid to stay alive and find a way to communicate with Earth. Weir's meticulous attention to scientific accuracy and his engaging, witty narrative make 'The Martian' a thrilling and inspiring read. The novel's exploration of human resilience and the spirit of discovery resonates deeply, offering a testament to the power of perseverance and innovation.",
        "https://images-na.ssl-images-amazon.com/images/I/91M2Xf36SML.jpg",4]
    ],
    Fantasy: [
        ["The Hobbit", "J.R.R. Tolkien", "The prelude to the Lord of the Rings, following the journey of Bilbo Baggins as he embarks on an adventure with dwarves to reclaim their homeland.",
        "J.R.R. Tolkien's 'The Hobbit' is a charming and enchanting adventure that transports readers to the magical world of Middle-earth. The story follows Bilbo Baggins, a hobbit who reluctantly leaves his peaceful home to join a group of dwarves on a quest to reclaim their homeland from the dragon Smaug. Tolkien's masterful storytelling and rich imagination bring to life a world filled with wondrous creatures, epic battles, and timeless themes of courage, friendship, and personal growth. Bilbo's transformation from a timid and reluctant hero to a brave and resourceful adventurer is both heartwarming and inspiring. 'The Hobbit' is a delightful prelude to the more epic and complex 'Lord of the Rings' trilogy, but stands on its own as a beloved classic of fantasy literature.",
        "https://images-na.ssl-images-amazon.com/images/I/91b0C2YNSrL.jpg",5],
        ["Harry Potter and the Sorcerer's Stone", "J.K. Rowling", "The first book in the Harry Potter series, introducing a young wizard and his adventures at Hogwarts School of Witchcraft and Wizardry.",
        "J.K. Rowling's 'Harry Potter and the Sorcerer's Stone' is the beginning of one of the most beloved and influential fantasy series of all time. The novel introduces readers to Harry Potter, an orphaned boy who discovers on his eleventh birthday that he is a wizard. Harry's journey to Hogwarts School of Witchcraft and Wizardry, where he makes lifelong friends and uncovers the truth about his parents' death, is filled with magic, mystery, and adventure. Rowling's rich world-building, memorable characters, and captivating storytelling have enchanted readers of all ages, making this book a timeless classic and the start of an extraordinary literary phenomenon.",
        "https://images-na.ssl-images-amazon.com/images/I/81YOuOGFCJL.jpg",5],
        ["A Game of Thrones", "George R.R. Martin", "The first book in the A Song of Ice and Fire series, a fantasy epic of politics, war, and intrigue in the Seven Kingdoms of Westeros.",
        "George R.R. Martin's 'A Game of Thrones' is the inaugural book in the epic fantasy series 'A Song of Ice and Fire.' Set in the fictional continents of Westeros and Essos, the novel weaves a complex tale of political intrigue, war, and betrayal among noble families vying for control of the Iron Throne. Martin's intricate plotting, multifaceted characters, and willingness to subvert traditional fantasy tropes have earned the series critical acclaim and a massive following. 'A Game of Thrones' introduces readers to a richly detailed world where honor and ambition collide, and where the line between hero and villain is often blurred. The novel's blend of medieval history, mythology, and gritty realism makes it a compelling and immersive read.",
        "https://images-na.ssl-images-amazon.com/images/I/91dSMhdIzTL.jpg",5],
        ["The Name of the Wind", "Patrick Rothfuss", "A fantasy novel that follows the life of a gifted young man who grows up to become a legendary figure.",
        "Patrick Rothfuss's 'The Name of the Wind' is a beautifully written and intricately crafted fantasy novel that follows the life of Kvothe, a gifted young man who becomes a legendary figure. The narrative is framed as an autobiographical account, with Kvothe recounting his adventures and experiences to a chronicler. Rothfuss's lyrical prose, richly developed world, and deep characterizations create a captivating and immersive reading experience. The novel explores themes of knowledge, power, and the nature of heroism, offering a fresh and engaging take on the traditional hero's journey. 'The Name of the Wind' is a must-read for fantasy enthusiasts, promising a profound and memorable literary journey.",
        "https://images-na.ssl-images-amazon.com/images/I/91b5f2e8Y9L.jpg",4],
        ["The Way of Kings", "Brandon Sanderson", "The first book in The Stormlight Archive, an epic fantasy series set in the world of Roshar, where magical storms shape the landscape and people.",
        "Brandon Sanderson's 'The Way of Kings' is the first installment in The Stormlight Archive, a grand and ambitious epic fantasy series. Set in the world of Roshar, the novel introduces readers to a land ravaged by magical storms and inhabited by diverse cultures and creatures. The story follows multiple characters, including Kaladin, a disgraced soldier turned slave; Shallan, a young scholar with a dark secret; and Dalinar, a nobleman haunted by visions. Sanderson's masterful world-building, complex plot, and richly developed characters create an immersive and thrilling reading experience. 'The Way of Kings' sets the stage for a sweeping saga of magic, warfare, and the struggle for power, making it a must-read for fantasy fans.",
        "https://images-na.ssl-images-amazon.com/images/I/91vYr3xK3FL.jpg",5]
    ],
    Mystery: [
        ["The Girl with the Dragon Tattoo", "Stieg Larsson", "A mystery novel about a journalist and a hacker who investigate the disappearance of a wealthy man's niece.",
        "Stieg Larsson's 'The Girl with the Dragon Tattoo' is a gripping and intricately plotted mystery that keeps readers on the edge of their seats. The novel introduces readers to Mikael Blomkvist, a disgraced journalist, and Lisbeth Salander, a brilliant but troubled hacker, as they team up to solve the decades-old disappearance of a wealthy industrialist's niece. Larsson's skillful weaving of complex characters, dark secrets, and unexpected twists creates a narrative that is both suspenseful and deeply engaging. The novel delves into themes of corruption, abuse, and redemption, painting a stark picture of societal dysfunction while celebrating the resilience and resourcefulness of its protagonists. 'The Girl with the Dragon Tattoo' is a compelling start to the Millennium Trilogy, offering a dark, thrilling, and thought-provoking read.",
        "https://images-na.ssl-images-amazon.com/images/I/81EVdQKxwLL.jpg",5],
        ["Gone Girl", "Gillian Flynn", "A psychological thriller about a husband who becomes the prime suspect in the disappearance of his wife.",
        "Gillian Flynn's 'Gone Girl' is a masterfully crafted psychological thriller that delves into the dark complexities of marriage and media manipulation. The novel centers on Nick and Amy Dunne, a seemingly perfect couple whose relationship unravels when Amy goes missing on their fifth wedding anniversary. As evidence mounts against Nick, Flynn skillfully alternates between his perspective and Amy's diary entries, revealing a web of deceit and manipulation. The novel's shocking twists and unreliable narrators keep readers guessing until the very end. 'Gone Girl' is a gripping exploration of love, betrayal, and the destructive power of secrets, making it a standout in the mystery and thriller genre.",
        "https://images-na.ssl-images-amazon.com/images/I/81WxZzMLy1L.jpg",4],
        ["The Da Vinci Code", "Dan Brown", "A mystery thriller that follows a symbologist and a cryptologist as they uncover a secret hidden by the Catholic Church.",
        "Dan Brown's 'The Da Vinci Code' is a fast-paced and intellectually stimulating mystery thriller that explores the intersection of history, religion, and art. The novel follows Robert Langdon, a Harvard symbologist, and Sophie Neveu, a French cryptologist, as they investigate the murder of the curator of the Louvre Museum. Their quest leads them to uncover a series of clues hidden in famous artworks, ultimately revealing a secret that has been protected by the Catholic Church for centuries. Brown's intricate plotting, compelling characters, and thought-provoking themes have made 'The Da Vinci Code' a global phenomenon, sparking discussions and debates about history and faith.",
        "https://images-na.ssl-images-amazon.com/images/I/81VsRERPtNL.jpg",4],
        ["Big Little Lies", "Liane Moriarty", "A mystery novel that delves into the lives of three women, each dealing with their own secrets and lies, culminating in a shocking murder.",
        "Liane Moriarty's 'Big Little Lies' is a captivating and intricately woven mystery that delves into the lives of three women living in a seaside town in Australia. The novel explores the complex dynamics of friendship, family, and community as it unravels the secrets and lies that bind the characters together. Through the perspectives of Madeline, Celeste, and Jane, Moriarty paints a vivid portrait of the pressures and challenges faced by women, culminating in a shocking and suspenseful murder investigation. 'Big Little Lies' is both a gripping thriller and a poignant exploration of the impact of violence and deception on individuals and their relationships.",
        "https://images-na.ssl-images-amazon.com/images/I/81F6ElbDnpL.jpg",4],
        ["In the Woods", "Tana French", "A psychological mystery about a detective who investigates the murder of a young girl, while confronting his own traumatic past.",
        "Tana French's 'In the Woods' is a haunting and psychologically complex mystery that follows Detective Rob Ryan as he investigates the murder of a young girl in a small Irish town. The case forces Ryan to confront his own traumatic past, as it bears eerie similarities to an unsolved disappearance from his childhood. French's evocative prose, rich character development, and intricate plotting create a compelling and immersive narrative that delves into themes of memory, trauma, and the elusive nature of truth. 'In the Woods' is a masterful blend of suspense and literary depth, offering a gripping and thought-provoking read.",
        "https://images-na.ssl-images-amazon.com/images/I/81pPDADsbJL.jpg",4]
    ],
    HistoricalFiction: [
        ["The Book Thief", "Markus Zusak", "A story set in Nazi Germany, narrated by Death, about a young girl who finds solace in stealing books and sharing them with others.",
        "Markus Zusak's 'The Book Thief' is a poignant and heart-wrenching tale set against the grim backdrop of Nazi Germany. Narrated by Death, the novel follows young Liesel Meminger, who finds solace in stealing books and sharing them with her neighbors during the horrors of World War II. Zusak's lyrical prose and unique narrative perspective offer a deeply moving and original exploration of the human spirit's resilience in the face of unimaginable suffering. The relationships Liesel forms with her foster parents, her friends, and the Jewish man hiding in her basement are beautifully rendered, highlighting the power of words and stories to provide comfort and hope. 'The Book Thief' is a profound and unforgettable story of love, loss, and the enduring power of literature.",
        "https://images-na.ssl-images-amazon.com/images/I/81eB+7+CkUL.jpg",5],
        ["All the Light We Cannot See", "Anthony Doerr", "A novel set during World War II, following the parallel lives of a blind French girl and a German boy whose paths eventually cross.",
        "Anthony Doerr's 'All the Light We Cannot See' is a beautifully crafted and emotionally powerful novel set against the backdrop of World War II. The story follows the parallel lives of Marie-Laure LeBlanc, a blind French girl who flees Paris with her father, and Werner Pfennig, a German boy with a talent for radio technology who is recruited by the Nazi regime. Doerr's exquisite prose and meticulous attention to detail bring to life the struggles, hopes, and resilience of his characters. As their paths eventually converge, the novel explores themes of survival, resistance, and the transformative power of human connection. 'All the Light We Cannot See' is a deeply moving and unforgettable work of historical fiction.",
        "https://images-na.ssl-images-amazon.com/images/I/81KJ1l-9z7L.jpg",4],
        ["The Nightingale", "Kristin Hannah", "A story about two sisters in Nazi-occupied France and their struggles and sacrifices during World War II.",
        "Kristin Hannah's 'The Nightingale' is a powerful and evocative novel that tells the story of two sisters, Vianne and Isabelle, in Nazi-occupied France during World War II. The novel vividly portrays the sisters' courage, resilience, and sacrifices as they navigate the horrors of war. Vianne, who is left behind to care for her daughter, must endure the occupation and make impossible choices to protect her loved ones. Meanwhile, Isabelle joins the French Resistance, risking her life to fight against the Nazis. Hannah's compelling storytelling and richly drawn characters create an immersive and emotional reading experience that highlights the strength and bravery of women in wartime. 'The Nightingale' is a testament to the enduring human spirit and the power of love and sacrifice.",
        "https://images-na.ssl-images-amazon.com/images/I/91rIQz5d2bL.jpg",4],
        ["The Help", "Kathryn Stockett", "A novel set in 1960s Mississippi, exploring the relationships between three women and the social dynamics of race and class.",
        "Kathryn Stockett's 'The Help' is a poignant and thought-provoking novel set in 1960s Mississippi that explores the complex relationships between three women: Aibileen, an African American maid; Minny, her outspoken friend and fellow maid; and Skeeter, a young white journalist. The novel delves into the social dynamics of race and class as Skeeter decides to write a book from the perspective of the maids, revealing the harsh realities and injustices they face. Stockett's rich characterizations, engaging narrative, and incisive social commentary create a compelling and emotionally resonant story. 'The Help' is a powerful exploration of courage, friendship, and the fight for equality.",
        "https://images-na.ssl-images-amazon.com/images/I/81DFav5Y9dL.jpg",5],
        ["The Pillars of the Earth", "Ken Follett", "An epic historical novel set in 12th-century England, centered around the construction of a cathedral and the lives of the people involved.",
        "Ken Follett's 'The Pillars of the Earth' is a sweeping and immersive epic set in 12th-century England. The novel centers around the construction of a magnificent cathedral in the fictional town of Kingsbridge and follows the lives of the people involved in its creation. Follett's richly detailed narrative brings to life the political intrigue, social upheaval, and personal struggles of the era. The story weaves together the lives of a diverse cast of characters, including the visionary builder Tom, the resourceful and determined Aliena, and the ruthless and ambitious William. 'The Pillars of the Earth' is a masterful blend of historical fiction and drama, offering a captivating and unforgettable reading experience.",
        "https://images-na.ssl-images-amazon.com/images/I/81QwQoIxfFL.jpg",4]
    ]
}

return{booksDictionary};
  }
}
</script>

<style scoped>
  .flow {
    display: flex;
    flex-wrap: wrap;
    justify-content: left;
    margin-top: 20px;
    margin-bottom: 20px;
  }
  .heading {
   /* center align text */
    text-align: center;
    margin-top: 20px;
    margin-bottom: 20px;
    background: rgba(11, 216, 216, 0.464);
    border-radius: 10px;
  }
  /* .text-red {
    color: red;
  } */
</style>
