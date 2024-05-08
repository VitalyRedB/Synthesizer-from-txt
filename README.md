# Synthesizer-from-txt
import pyttsx3
engine = pyttsx3.init()
def text_to_speech(file_path):
    try:
        with open(file_path, 'r', encoding='utf-8') as file:
            text = file.read()
            say_text(text)
    except:
        text = "Нет файла для работы. Добавьте файл text.txt в папку со мной для озвучивания. Перезапусти программу. До новых встреч."
        say_text(text)
def say_text(text):
    print(text)
    engine.say(text)
    engine.runAndWait()

text = "Привет. Я синтезатор речи Алиса. Введите скорость синтеза. Среднее - 150 слов в минуту. "
say_text(text)
engine.setProperty('rate', int(input()))
text_to_speech('text.txt')

