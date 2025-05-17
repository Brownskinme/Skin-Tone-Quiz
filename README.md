``html
    body {
        font-family: 'Montserrat', sans-serif;
        background: var(--background);
        color: var(--text);
        min-height: 100vh;
    }
    
    h1, h2, h3, h4 {
        font-family: 'Cormorant Garamond', serif;
    }
    
    .option-card {
        transition: all 0.3s ease;
        cursor: pointer;
        border: 1px solid rgba(139, 90, 43, 0.2);
    }
    
    .option-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(139, 90, 43, 0.15);
        border-color: var(--secondary);
    }
    
    .selected {
        border: 2px solid var(--secondary);
        background-color: rgba(212, 175, 55, 0.1);
        transform: translateY(-5px);
    }
    
    .skin-tone {
        width: 100px;
        height: 100px;
        border-radius: 50%;
        margin: 0 auto;
        border: 3px solid #fff;
        box-shadow: 0 4px 15px rgba(139, 90, 43, 0.2);
    }
    
    .product-card {
        transition: all 0.3s ease;
        border: 1px solid rgba(139, 90, 43, 0.2);
    }
    
    .product-card:hover {
        transform: translateY(-5px);
        box-shadow: 0 10px 20px rgba(139, 90, 43, 0.15);
        border-color: var(--secondary);
    }
    
    .color-swatch {
        width: 50px;
        height: 50px;
        border-radius: 50%;
        margin: 0 auto;
        border: 2px solid #fff;
        box-shadow: 0 2px 8px rgba(139, 90, 43, 0.15);
    }
    
    .gold-gradient {
        background: linear-gradient(135deg, #D4AF37 0%, #F9F295 50%, #D4AF37 100%);
    }
    
    .btn-primary {
        background: linear-gradient(135deg, var(--accent), var(--secondary));
        color: white;
        transition: all 0.3s ease;
    }
    
    .btn-primary:hover {
        transform: translateY(-2px);
        box-shadow: 0 5px 15px rgba(139, 90, 43, 0.3);
    }
    
    .quiz-container {
        background-color: white;
        border-radius: 20px;
        box-shadow: 0 10px 30px rgba(139, 90, 43, 0.1);
    }
    
    .result-badge {
        display: inline-block;
        padding: 8px 16px;
        border-radius: 20px;
        font-size: 14px;
        font-weight: 600;
        margin-right: 8px;
        margin-bottom: 8px;
    }
    
    .scripture-box {
        background-color: rgba(212, 175, 55, 0.1);
        border-left: 4px solid var(--secondary);
        padding: 15px;
        margin: 20px 0;
        font-style: italic;
    }
    
    .affirmation-box {
        text-align: center;
        font-weight: 500;
        font-size: 1.1rem;
        padding: 15px;
        margin: 20px 0;
        color: var(--primary);
    }
    
    .season-badge {
        display: inline-block;
        padding: 6px 12px;
        border-radius: 15px;
        font-size: 13px;
        margin-right: 6px;
        margin-bottom: 6px;
    }
    
    .question-section {
        position: relative;
        padding: 30px;
        margin-bottom: 30px;
        border-radius: 20px;
        background-color: white;
        box-shadow: 0 5px 20px rgba(139, 90, 43, 0.1);
    }
    
    .question-number {
        position: absolute;
        top: -15px;
        left: 30px;
        width: 40px;
        height: 40px;
        display: flex;
        align-items: center;
        justify-content: center;
        background: var(--secondary);
        color: white;
        border-radius: 50%;
        font-weight: bold;
        box-shadow: 0 3px 10px rgba(139, 90, 43, 0.2);
    }
    
    .divider {
        height: 3px;
        background: linear-gradient(90deg, var(--accent), var(--secondary), var(--accent));
        border-radius: 3px;
        margin: 50px 0;
    }
    
    .fade-in {
        animation: fadeIn 0.5s ease-in;
    }
    
    @keyframes fadeIn {
        from { opacity: 0; }
        to { opacity: 1; }
    }
    
    .sparkle {
        position: absolute;
        pointer-events: none;
        width: 20px;
        height: 20px;
        background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='20' height='20' viewBox='0 0 20 20'%3E%3Cpath d='M10 0L12.5 7.5L20 10L12.5 12.5L10 20L7.5 12.5L0 10L7.5 7.5L10 0Z' fill='%23D4AF37'/%3E%3C/svg%3E");
        background-size: contain;
        animation: sparkle 1.5s linear infinite;
        opacity: 0;
    }
    
    @keyframes sparkle {
        0% { transform: scale(0); opacity: 0; }
        50% { transform: scale(1); opacity: 1; }
        100% { transform: scale(0); opacity: 0; }
    }
    
    .scroll-to-results {
        position: fixed;
        bottom: 30px;
        right: 30px;
        z-index: 100;
        padding: 15px;
        border-radius: 50%;
        box-shadow: 0 5px 15px rgba(139, 90, 43, 0.3);
        display: none;
    }
    
    /* Embed container styles */
    #brownskin-quiz-container {
        width: 100%;
        max-width: 1000px;
        margin: 0 auto;
        border-radius: 20px;
        overflow: hidden;
    }
</style>
    <div class="mb-10">
        <h2 class="text-2xl font-semibold mb-6 text-center" style="color: var(--primary);">Answer All Questions Below</h2>
        <p class="text-center mb-8">Your personalized results will appear at the bottom of the page</p>
    </div>

    <!-- Question 1 -->
    <div class="question-section" id="question-1">
        <div class="question-number">1</div>
        <h3 class="text-xl font-semibold mb-6">Which best describes your skin's overall tone?</h3>
        <div class="options-container">
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="1" data-value="deep-ebony" onclick="selectOption(this, 1, 'deep-ebony')">
                <p class="text-lg">Deep, rich dark brown with cool undertones</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="1" data-value="rich-mahogany" onclick="selectOption(this, 1, 'rich-mahogany')">
                <p class="text-lg">Rich, reddish-brown with warm undertones</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="1" data-value="golden-bronze" onclick="selectOption(this, 1, 'golden-bronze')">
                <p class="text-lg">Medium-deep brown with golden undertones</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="1" data-value="warm-honey" onclick="selectOption(this, 1, 'warm-honey')">
                <p class="text-lg">Medium brown with warm yellow undertones</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="1" data-value="caramel-glow" onclick="selectOption(this, 1, 'caramel-glow')">
                <p class="text-lg">Light to medium brown with neutral undertones</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="1" data-value="butterscotch-beige" onclick="selectOption(this, 1, 'butterscotch-beige')">
                <p class="text-lg">Light brown with golden beige undertones</p>
            </div>
        </div>
    </div>

    <!-- Question 2 -->
    <div class="question-section" id="question-2">
        <div class="question-number">2</div>
        <h3 class="text-xl font-semibold mb-6">How does your skin react to the sun?</h3>
        <div class="options-container">
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="2" data-value="warm" onclick="selectOption(this, 2, 'warm')">
                <p class="text-lg">Rarely burns, tans easily and evenly</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="2" data-value="neutral" onclick="selectOption(this, 2, 'neutral')">
                <p class="text-lg">Sometimes burns, then develops a deep tan</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="2" data-value="cool" onclick="selectOption(this, 2, 'cool')">
                <p class="text-lg">Rarely burns, but can develop uneven tone</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="2" data-value="warm" onclick="selectOption(this, 2, 'warm')">
                <p class="text-lg">Never burns, tans very deeply</p>
            </div>
        </div>
    </div>

    <!-- Question 3 -->
    <div class="question-section" id="question-3">
        <div class="question-number">3</div>
        <h3 class="text-xl font-semibold mb-6">What color are the veins on your wrist?</h3>
        <div class="options-container">
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="3" data-value="warm" onclick="selectOption(this, 3, 'warm')">
                <p class="text-lg">Greenish or olive</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="3" data-value="cool" onclick="selectOption(this, 3, 'cool')">
                <p class="text-lg">Blue or purple</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="3" data-value="neutral" onclick="selectOption(this, 3, 'neutral')">
                <p class="text-lg">A mix of both or hard to tell</p>
            </div>
        </div>
    </div>

    <!-- Question 4 -->
    <div class="question-section" id="question-4">
        <div class="question-number">4</div>
        <h3 class="text-xl font-semibold mb-6">Which jewelry metals look best against your skin?</h3>
        <div class="options-container">
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="4" data-value="warm" onclick="selectOption(this, 4, 'warm')">
                <p class="text-lg">Gold or bronze</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="4" data-value="cool" onclick="selectOption(this, 4, 'cool')">
                <p class="text-lg">Silver or platinum</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="4" data-value="neutral" onclick="selectOption(this, 4, 'neutral')">
                <p class="text-lg">Both look equally good</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="4" data-value="warm" onclick="selectOption(this, 4, 'warm')">
                <p class="text-lg">Rose gold</p>
            </div>
        </div>
    </div>

    <!-- Question 5 -->
    <div class="question-section" id="question-5">
        <div class="question-number">5</div>
        <h3 class="text-xl font-semibold mb-6">What's your main skincare concern?</h3>
        <div class="options-container">
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="5" data-value="even" onclick="selectOption(this, 5, 'even')">
                <p class="text-lg">Uneven skin tone or dark spots</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="5" data-value="glow" onclick="selectOption(this, 5, 'glow')">
                <p class="text-lg">Dryness or lack of glow</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="5" data-value="texture" onclick="selectOption(this, 5, 'texture')">
                <p class="text-lg">Oiliness or texture issues</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="5" data-value="calm" onclick="selectOption(this, 5, 'calm')">
                <p class="text-lg">Sensitivity or redness</p>
            </div>
            <div class="option-card p-5 rounded-xl mb-4 hover:bg-gray-50" data-question="5" data-value="pigment" onclick="selectOption(this, 5, 'pigment')">
                <p class="text-lg">Hyperpigmentation</p>
            </div>
        </div>
    </div>

    <div class="divider"></div>

    <!-- Results Section -->
    <div id="results-section">
        <div class="text-center mb-10">
            <h2 class="text-3xl font-bold mb-4" style="color: var(--primary);">Your Results</h2>
            <p id="results-pending" class="text-lg">Please answer all questions above to see your personalized results.</p>
            <div id="results-content" class="hidden">
                <!-- Results will be dynamically inserted here -->
            </div>
        </div>
    </div>
    
    <footer class="text-center mt-10 text-sm text-gray-500">
        <p>© 2023 BrownSkin.me - Version 6.0</p>
        <p class="mt-2">Created with ❤️ for beautiful brown skin</p>
    </footer>
</div>

<!-- Scroll to Results Button -->
<button id="scroll-to-results-btn" class="scroll-to-results btn-primary" onclick="scrollToResults()">
    👇
</button>

<script>
    // Skin tone results data with product URLs
    const skinToneResults = [
        {
            type: "deep-ebony",
            name: "Deep Ebony",
            description: "Your skin has a rich, deep dark brown tone with cool undertones that radiates elegance and strength.",
            colorCode: "#2D1A12",
            bestColors: ["Emerald green", "Royal blue", "Deep purple", "Chocolate", "Caramel", "Burnt orange"],
            products: [
                { 
                    name: "100% Cotton Wrap Dress in Emerald Green", 
                    price: "$89.99", 
                    image: "👗",
                    url: "https://brownskin.me/products/cotton-wrap-dress-emerald"
                },
                { 
                    name: "Relaxed Fit Hoodie in Royal Blue", 
                    price: "$59.99", 
                    image: "👕",
                    url: "https://brownskin.me/products/relaxed-hoodie-royal-blue"
                }
            ],
            skincareFocus: "Even tone + radiance",
            diy: "Turmeric & Honey Mask",
            affirmation: "My melanin is majestic...",
            scripture: "Psalm 139:14 - I praise you because I am fearfully and wonderfully made; your works are wonderful, I know that full well.",
            complementaryColors: [
                { name: "Emerald Green", code: "#50C878" },
                { name: "Royal Blue", code: "#4169E1" },
                { name: "Deep Purple", code: "#483D8B" },
                { name: "Chocolate", code: "#7B3F00" },
                { name: "Burnt Orange", code: "#CC5500" }
            ],
            seasonalColors: {
                spring: ["Soft Yellow", "Coral", "Peach"],
                summer: ["Royal Blue", "Emerald Green", "Deep Red"],
                fall: ["Burnt Orange", "Chocolate Brown", "Olive"],
                winter: ["Deep Purple", "Navy", "Crisp White"]
            }
        },
        {
            type: "rich-mahogany",
            name: "Rich Mahogany",
            description: "Your skin has a beautiful rich, reddish-brown tone with warm undertones that exudes warmth and depth.",
            colorCode: "#4E2A1E",
            bestColors: ["Brick red", "Burgundy", "Golden yellow", "Deep teal"],
            products: [
                { 
                    name: "Organic Cotton Turtleneck in Burgundy", 
                    price: "$69.99", 
                    image: "👚",
                    url: "https://brownskin.me/products/cotton-turtleneck-burgundy"
                },
                { 
                    name: "Wide-Leg Linen Pants in Deep Teal", 
                    price: "$79.99", 
                    image: "👖",
                    url: "https://brownskin.me/products/linen-pants-teal"
                }
            ],
            skincareFocus: "Glow + texture balance",
            diy: "Rosehip & Aloe Glow Serum",
            affirmation: "I radiate power, peace, and purpose.",
            scripture: "Isaiah 60:1 - Arise, shine, for your light has come, and the glory of the LORD rises upon you.",
            complementaryColors: [
                { name: "Brick Red", code: "#A52A2A" },
                { name: "Burgundy", code: "#800020" },
                { name: "Golden Yellow", code: "#FFDF00" },
                { name: "Deep Teal", code: "#008080" },
                { name: "Warm Brown", code: "#964B00" }
            ],
            seasonalColors: {
                spring: ["Golden Yellow", "Warm Peach", "Coral"],
                summer: ["Deep Teal", "Bright Red", "Turquoise"],
                fall: ["Burgundy", "Rust", "Amber"],
                winter: ["Ruby Red", "Forest Green", "Navy"]
            }
        },
        {
            type: "golden-bronze",
            name: "Golden Bronze",
            description: "Your skin has a medium-deep brown tone with beautiful golden undertones that captures light beautifully.",
            colorCode: "#996515",
            bestColors: ["Olive green", "Moss green", "Warm brown", "Peach"],
            products: [
                { 
                    name: "Sleeveless Maxi Dress in Olive", 
                    price: "$89.99", 
                    image: "👗",
                    url: "https://brownskin.me/products/maxi-dress-olive"
                },
                { 
                    name: "High-Waisted Trousers in Warm Brown", 
                    price: "$79.99", 
                    image: "👖",
                    url: "https://brownskin.me/products/trousers-warm-brown"
                }
            ],
            skincareFocus: "Oil balance + softness",
            diy: "Balancing Clay Mask (bentonite + aloe + ACV)",
            affirmation: "My light is balanced, strong, and sacred.",
            scripture: "Proverbs 31:25 - She is clothed with strength and dignity; she can laugh at the days to come.",
            complementaryColors: [
                { name: "Olive Green", code: "#556B2F" },
                { name: "Moss Green", code: "#8A9A5B" },
                { name: "Warm Brown", code: "#964B00" },
                { name: "Peach", code: "#FFDAB9" },
                { name: "Terracotta", code: "#E2725B" }
            ],
            seasonalColors: {
                spring: ["Peach", "Light Coral", "Soft Yellow"],
                summer: ["Bright Green", "Turquoise", "Coral Red"],
                fall: ["Olive Green", "Terracotta", "Mustard"],
                winter: ["Forest Green", "Burgundy", "Navy"]
            }
        },
        {
            type: "warm-honey",
            name: "Warm Honey",
            description: "Your skin has a medium brown tone with warm yellow undertones that gives you a natural glow.",
            colorCode: "#C2956E",
            bestColors: ["Coral", "Warm pink", "Mustard", "Soft taupe"],
            products: [
                { 
                    name: "Off-Shoulder Top in Coral", 
                    price: "$59.99", 
                    image: "👚",
                    url: "https://brownskin.me/products/off-shoulder-top-coral"
                },
                { 
                    name: "Linen Blazer in Mustard", 
                    price: "$89.99", 
                    image: "🧥",
                    url: "https://brownskin.me/products/linen-blazer-mustard"
                }
            ],
            skincareFocus: "Hydration + vibrancy",
            diy: "Rosewater & Aloe Hydrating Gel",
            affirmation: "I am sweet, glowing, and divinely nourished.",
            scripture: "Song of Solomon 1:5 - Dark am I, yet lovely, daughters of Jerusalem, dark like the tents of Kedar, like the tent curtains of Solomon.",
            complementaryColors: [
                { name: "Coral", code: "#FF7F50" },
                { name: "Warm Pink", code: "#FF69B4" },
                { name: "Mustard", code: "#E1AD01" },
                { name: "Soft Taupe", code: "#D2B48C" },
                { name: "Sage Green", code: "#BCB88A" }
            ],
            seasonalColors: {
                spring: ["Coral", "Peach", "Soft Yellow"],
                summer: ["Bright Pink", "Turquoise", "Lime Green"],
                fall: ["Mustard", "Rust", "Olive"],
                winter: ["Burgundy", "Forest Green", "Navy"]
            }
        },
        {
            type: "caramel-glow",
            name: "Caramel Glow",
            description: "Your skin has a light to medium brown tone with neutral undertones that gives you versatility with colors.",
            colorCode: "#C68642",
            bestColors: ["Navy", "Sky blue", "Lavender", "Light gray"],
            products: [
                { 
                    name: "Cotton Wrap Skirt in Navy", 
                    price: "$69.99", 
                    image: "👗",
                    url: "https://brownskin.me/products/wrap-skirt-navy"
                },
                { 
                    name: "Oversized Sweatshirt in Light Gray", 
                    price: "$59.99", 
                    image: "👕",
                    url: "https://brownskin.me/products/oversized-sweatshirt-gray"
                }
            ],
            skincareFocus: "Tone clarity + brightness",
            diy: "Brightening Scrub (oat + almond + rosewater)",
            affirmation: "My glow is golden and intentional.",
            scripture: "Matthew 5:16 - In the same way, let your light shine before others, that they may see your good deeds and glorify your Father in heaven.",
            complementaryColors: [
                { name: "Navy", code: "#000080" },
                { name: "Sky Blue", code: "#87CEEB" },
                { name: "Lavender", code: "#E6E6FA" },
                { name: "Light Gray", code: "#D3D3D3" },
                { name: "Soft Pink", code: "#FFB6C1" }
            ],
            seasonalColors: {
                spring: ["Soft Pink", "Light Blue", "Peach"],
                summer: ["Sky Blue", "Lavender", "Coral"],
                fall: ["Camel", "Rust", "Olive"],
                winter: ["Navy", "Burgundy", "Crisp White"]
            }
        },
        {
            type: "butterscotch-beige",
            name: "Butterscotch Beige",
            description: "Your skin has a light brown tone with golden beige undertones that pairs beautifully with soft colors.",
            colorCode: "#E3A857",
            bestColors: ["Blush pink", "Mint", "Powder blue", "Rich brown"],
            products: [
                { 
                    name: "Knit Sweater in Blush Pink", 
                    price: "$69.99", 
                    image: "🧶",
                    url: "https://brownskin.me/products/knit-sweater-blush"
                },
                { 
                    name: "Tailored Jumpsuit in Rich Brown", 
                    price: "$99.99", 
                    image: "👗",
                    url: "https://brownskin.me/products/tailored-jumpsuit-brown"
                }
            ],
            skincareFocus: "Soothing + softness",
            diy: "Coconut Milk & Chamomile Cleanser",
            affirmation: "I am soft, strong, and sacred in every way.",
            scripture: "Zephaniah 3:17 - The LORD your God is with you, the Mighty Warrior who saves. He will take great delight in you; in his love he will no longer rebuke you, but will rejoice over you with singing.",
            complementaryColors: [
                { name: "Blush Pink", code: "#FFB6C1" },
                { name: "Mint", code: "#98FB98" },
                { name: "Powder Blue", code: "#B0E0E6" },
                { name: "Rich Brown", code: "#8B4513" },
                { name: "Soft Cream", code: "#FFFDD0" }
            ],
            seasonalColors: {
                spring: ["Blush Pink", "Mint", "Soft Yellow"],
                summer: ["Powder Blue", "Soft Lavender", "Coral"],
                fall: ["Rich Brown", "Mustard", "Olive"],
                winter: ["Burgundy", "Navy", "Crisp White"]
            }
        }
    ];

    // Quiz state
    let answers = {
        1: null,
        2: null,
        3: null,
        4: null,
        5: null
    };

    // DOM elements
    const resultsContent = document.getElementById('results-content');
    const resultsPending = document.getElementById('results-pending');
    const scrollToResultsBtn = document.getElementById('scroll-to-results-btn');

    // Initialize quiz
    function initQuiz() {
        createSparkles();
        checkAllAnswered();
    }

    // Create sparkle effect
    function createSparkles() {
        const container = document.querySelector('body');
        const sparkleCount = 15;
        
        for (let i = 0; i < sparkleCount; i++) {
            const sparkle = document.createElement('div');
            sparkle.classList.add('sparkle');
            
            // Random position
            const posX = Math.random() * window.innerWidth;
            const posY = Math.random() * window.innerHeight;
            sparkle.style.left = `${posX}px`;
            sparkle.style.top = `${posY}px`;
            
            // Random delay
            const delay = Math.random() * 2;
            sparkle.style.animationDelay = `${delay}s`;
            
            container.appendChild(sparkle);
        }
    }

    // Select option
    function selectOption(element, questionNumber, value) {
        // Remove selected class from all options in this question
        const options = document.querySelectorAll(`.option-card[data-question="${questionNumber}"]`);
        options.forEach(option => option.classList.remove('selected'));
        
        // Add selected class to clicked option
        element.classList.add('selected');
        
        // Store selected value
        answers[questionNumber] = value;
        
        // Check if all questions are answered
        checkAllAnswered();
        
        // Show scroll to results button
        scrollToResultsBtn.style.display = 'block';
    }

    // Check if all questions are answered
    function checkAllAnswered() {
        const allAnswered = Object.values(answers).every(answer => answer !== null);
        
        if (allAnswered) {
            showResults();
        }
    }

    // Calculate results
    function calculateResults() {
        // First question directly gives us the primary skin tone type
        return answers[1];
    }

    // Show results
    function showResults() {
        const resultType = calculateResults();
        const result = skinToneResults.find(r => r.type === resultType);
        
        // Hide pending message and show results
        resultsPending.classList.add('hidden');
        resultsContent.classList.remove('hidden');
        
        // Generate product cards
        let productCardsHTML = '';
        result.products.forEach(product => {
            productCardsHTML += `
                <div class="product-card bg-white rounded-xl overflow-hidden">
                    <div class="p-6 text-center">
                        <div class="text-5xl mb-4">${product.image}</div>
                        <h3 class="text-lg font-semibold">${product.name}</h3>
                        <p class="font-medium" style="color: var(--accent);">${product.price}</p>
                        <a href="${product.url}" target="_blank" class="mt-4 px-4 py-2 rounded-lg btn-primary inline-block">Add to Cart</a>
                    </div>
                </div>
            `;
        });
        
        // Generate color swatches
        let colorSwatchesHTML = '';
        result.complementaryColors.forEach(color => {
            colorSwatchesHTML += `
                <div class="text-center">
                    <div class="color-swatch" style="background-color: ${color.code}"></div>
                    <p class="text-sm mt-2">${color.name}</p>
                </div>
            `;
        });
        
        // Generate seasonal color guide
        let seasonalColorsHTML = '';
        Object.entries(result.seasonalColors).forEach(([season, colors]) => {
            let seasonColor;
            switch(season) {
                case 'spring': seasonColor = '#F9A826'; break;
                case 'summer': seasonColor = '#4ECDC4'; break;
                case 'fall': seasonColor = '#D35400'; break;
                case 'winter': seasonColor = '#34495E'; break;
            }
            
            seasonalColorsHTML += `
                <div class="mb-4">
                    <h4 class="font-semibold mb-2 capitalize">${season}</h4>
                    <div>
                        ${colors.map(color => `<span class="season-badge" style="background-color: ${seasonColor}20; color: ${seasonColor}">${color}</span>`).join('')}
                    </div>
                </div>
            `;
        });
        
        resultsContent.innerHTML = `
            <div class="text-center mb-10 fade-in">
                <div class="inline-block px-4 py-1 rounded-full text-sm font-semibold mb-4 gold-gradient text-white">
                    Your Perfect Match
                </div>
                <h2 class="text-4xl font-bold mb-4" style="color: var(--primary);">✨ ${result.name} ✨</h2>
                <div class="skin-tone mx-auto mb-6" style="background-color: ${result.colorCode};"></div>
                <p class="text-lg max-w-2xl mx-auto">${result.description}</p>
                
                <div class="flex flex-wrap justify-center gap-3 mt-6">
                    <div class="result-badge" style="background-color: rgba(212, 175, 55, 0.15); color: var(--primary);">
                        🔮 ${result.skincareFocus}
                    </div>
                </div>
            </div>
            
            <div class="mb-10 p-8 rounded-xl fade-in" style="background-color: rgba(212, 175, 55, 0.05);">
                <h3 class="text-2xl font-semibold mb-6 text-center" style="color: var(--primary);">🌈 Your Complementary Colors</h3>
                <p class="text-center mb-8">These colors will enhance your natural beauty and make your skin glow!</p>
                <div class="flex justify-center space-x-6 flex-wrap gap-y-6">
                    ${colorSwatchesHTML}
                </div>
            </div>
            
            <div class="mb-10 fade-in">
                <h3 class="text-2xl font-semibold mb-6 text-center" style="color: var(--primary);">👑 BrownSkin.me Recommendations</h3>
                <p class="text-center mb-8">Curated pieces in your perfect colors to enhance your natural beauty</p>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6">
                    ${productCardsHTML}
                </div>
            </div>
            
            <div class="mb-10 p-6 rounded-xl fade-in" style="background-color: rgba(212, 175, 55, 0.05);">
                <h3 class="text-xl font-semibold mb-4 text-center" style="color: var(--primary);">🧴 Skincare Focus</h3>
                <p class="text-center mb-2">${result.skincareFocus}</p>
                
                <div class="mt-6">
                    <h4 class="font-semibold text-center mb-2">DIY Beauty Recipe</h4>
                    <p class="text-center">${result.diy}</p>
                </div>
            </div>
            
            <div class="mb-10 fade-in">
                <div class="affirmation-box">
                    "✨ ${result.affirmation} ✨"
                </div>
                
                <div class="scripture-box">
                    ${result.scripture}
                </div>
            </div>
            
            <div class="mb-10 p-6 rounded-xl fade-in" style="background-color: rgba(212, 175, 55, 0.05);">
                <h3 class="text-xl font-semibold mb-4 text-center" style="color: var(--primary);">🍃 Seasonal Color Guide</h3>
                <div class="grid grid-cols-1 md:grid-cols-2 gap-6 mt-6">
                    ${seasonalColorsHTML}
                </div>
            </div>
            
            <div class="mt-12 text-center fade-in">
                <button class="px-8 py-3 rounded-lg btn-primary mb-4" onclick="resetQuiz()">Reset Quiz</button>
                <p class="mt-6">Share your beautiful results with friends!</p>
                <div class="flex justify-center space-x-4 mt-3">
                    <button class="p-2 rounded-full" style="background-color: var(--accent); color: white;">📱</button>
                    <button class="p-2 rounded-full" style="background-color: var(--accent); color: white;">📸</button>
                    <button class="p-2 rounded-full" style="background-color: var(--accent); color: white;">🐦</button>
                </div>
            </div>
        `;
    }

    // Reset quiz
    function resetQuiz() {
        // Reset answers
        answers = {
            1: null,
            2: null,
            3: null,
            4: null,
            5: null
        };
        
        // Reset selected options
        const options = document.querySelectorAll('.option-card');
        options.forEach(option => option.classList.remove('selected'));
        
        // Hide results and show pending message
        resultsContent.classList.add('hidden');
        resultsPending.classList.remove('hidden');
        
        // Hide scroll to results button
        scrollToResultsBtn.style.display = 'none';
        
        // Scroll to top
        window.scrollTo({ top: 0, behavior: 'smooth' });
    }

    // Scroll to results
    function scrollToResults() {
        document.getElementById('results-section').scrollIntoView({ behavior: 'smooth' });
    }

    // Initialize the quiz when page loads
    window.onload = initQuiz;
</script>
    // Set the source to your hosted quiz
    iframe.src = 'https://yourdomain.com/brownskin-quiz-v6.html'; // Replace with your actual URL
    
    // Add iframe to container
    document.getElementById('brownskin-quiz-embed').appendChild(iframe);
    
    // Make iframe responsive
    window.addEventListener('message', function(event) {
        if (event.data.type === 'quiz-height') {
            iframe.style.height = event.data.height + 'px';
        }
    }, false);
})();
