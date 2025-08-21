# Quiz

```python
import random

class QuestionGenerator:
    def __init__(self):
        self.questions = {
            "English": self.get_english_questions(),
            "Maths": self.get_maths_questions(),
            "Physics": self.get_physics_questions(),
            "Chemistry": self.get_chemistry_questions(),
            "Biology": self.get_biology_questions(),
            "SAT": self.get_sat_questions()
        }
    
    def get_english_questions(self):
        return [
            {
                "question": "Identify the grammatical error: 'Neither of the boys are coming to the party.'",
                "answer": "The error is subject-verb agreement. 'Neither' is singular and should take 'is' not 'are'."
            },
            {
                "question": "Which word is a synonym for 'ubiquitous'? a) rare b) scarce c) omnipresent d) limited",
                "answer": "c) omnipresent"
            },
            {
                "question": "Rewrite in passive voice: 'The committee will announce the results tomorrow.'",
                "answer": "The results will be announced by the committee tomorrow."
            },
            {
                "question": "What literary device is used in: 'The stars danced playfully in the moonlit sky'?",
                "answer": "Personification (giving human qualities to stars)"
            },
            {
                "question": "What is the past participle of the verb 'to swim'?",
                "answer": "swum"
            }
        ]
    
    def get_maths_questions(self):
        return [
            {
                "question": "Solve for x: 3x + 7 = 22",
                "answer": "x = 5"
            },
            {
                "question": "Calculate the area of a circle with radius 5 cm.",
                "answer": "78.54 cm² (using πr² with π=3.1416)"
            },
            {
                "question": "Simplify: (2x² + 3x - 5) + (4x² - 2x + 7)",
                "answer": "6x² + x + 2"
            },
            {
                "question": "Find y when x=3 in the equation y = 2x² - 4x + 1",
                "answer": "y = 7"
            }
        ]
    
    def get_physics_questions(self):
        return [
            {
                "question": "Calculate the force required to accelerate a 5 kg object at 3 m/s².",
                "answer": "15 N (using F = m × a)"
            },
            {
                "question": "Explain the difference between kinetic and potential energy.",
                "answer": "Kinetic energy is energy of motion, while potential energy is stored energy based on position or state."
            },
            {
                "question": "A car travels 150 km in 2 hours. What is its average speed in m/s?",
                "answer": "20.83 m/s (150 km = 150,000 m, 2 hours = 7200 s, speed = distance/time)"
            },
            {
                "question": "Describe Newton's Third Law of Motion.",
                "answer": "For every action, there is an equal and opposite reaction."
            }
        ]
    
    def get_chemistry_questions(self):
        return [
            {
                "question": "Balance the equation: H₂ + O₂ → H₂O",
                "answer": "2H₂ + O₂ → 2H₂O"
            },
            {
                "question": "What is the difference between an element and a compound?",
                "answer": "An element is a pure substance made of one type of atom. A compound is made of two or more elements chemically combined."
            },
            {
                "question": "How many moles are in 25 grams of water (H₂O)?",
                "answer": "Approximately 1.39 moles (molar mass of H₂O is 18 g/mol)"
            },
            {
                "question": "Explain the process of electrolysis.",
                "answer": "Electrolysis is a process that uses electrical energy to drive a non-spontaneous chemical reaction."
            }
        ]
    
    def get_biology_questions(self):
        return [
            {
                "question": "Describe the process of photosynthesis.",
                "answer": "Photosynthesis is the process where plants convert light energy, water, and CO₂ into glucose and oxygen."
            },
            {
                "question": "What is the difference between mitosis and meiosis?",
                "answer": "Mitosis produces two identical diploid cells for growth and repair. Meiosis produces four genetically different haploid cells for reproduction."
            },
            {
                "question": "Explain how enzymes function as biological catalysts.",
                "answer": "Enzymes speed up chemical reactions by lowering the activation energy without being consumed in the process."
            },
            {
                "question": "Describe the structure of DNA.",
                "answer": "DNA is a double helix structure made of nucleotides containing a sugar-phosphate backbone and nitrogenous bases (A,T,C,G)."
            }
        ]
    
    def get_sat_questions(self):
        return [
            {
                "question": "If 3x - 7 = 17, what is the value of x?",
                "answer": "x = 8"
            },
            {
                "question": "In the equation y = 3x² - 2x + 5, what is y when x = -2?",
                "answer": "y = 21"
            },
            {
                "question": "The ratio of boys to girls is 3:5. If there are 24 students total, how many boys are there?",
                "answer": "9 boys (3/8 of 24)"
            },
            {
                "question": "A rectangle has length twice its width. If perimeter is 36 cm, what is the area?",
                "answer": "72 cm² (width=6cm, length=12cm)"
            }
        ]
    
    def display_questions(self, subject):
        if subject in self.questions:
            print(f"\n{subject} Questions:")
            print("=" * 50)
            for i, qa in enumerate(self.questions[subject], 1):
                print(f"{i}. {qa['question']}")
            
            show_answers = input("\nWould you like to see the answers? (yes/no): ").lower()
            if show_answers == 'yes':
                print(f"\n{subject} Answers:")
                print("=" * 50)
                for i, qa in enumerate(self.questions[subject], 1):
                    print(f"{i}. {qa['answer']}")
        else:
            print("Subject not found!")
    
    def display_all_questions(self):
        for subject in self.questions:
            self.display_questions(subject)
            input("\nPress Enter to continue to next subject...")
    
    def run(self):
        while True:
            print("\n" + "="*50)
            print("QUESTION GENERATOR")
            print("="*50)
            print("1. English (5 questions)")
            print("2. Maths (4 questions)")
            print("3. Physics (4 questions)")
            print("4. Chemistry (4 questions)")
            print("5. Biology (4 questions)")
            print("6. SAT (4 questions)")
            print("7. All subjects")
            print("8. Exit")
            
            choice = input("\nEnter your choice (1-8): ")
            
            if choice == '1':
                self.display_questions("English")
            elif choice == '2':
                self.display_questions("Maths")
            elif choice == '3':
                self.display_questions("Physics")
            elif choice == '4':
                self.display_questions("Chemistry")
            elif choice == '5':
                self.display_questions("Biology")
            elif choice == '6':
                self.display_questions("SAT")
            elif choice == '7':
                self.display_all_questions()
            elif choice == '8':
                print("Goodbye!")
                break
            else:
                print("Invalid choice! Please try again.")

# Run the program
if __name__ == "__main__":
    generator = QuestionGenerator()
    generator.run(
