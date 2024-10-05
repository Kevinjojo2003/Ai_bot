{
  "nbformat": 4,
  "nbformat_minor": 0,
  "metadata": {
    "colab": {
      "provenance": []
    },
    "kernelspec": {
      "name": "python3",
      "display_name": "Python 3"
    },
    "language_info": {
      "name": "python"
    }
  },
  "cells": [
    {
      "cell_type": "code",
      "execution_count": 3,
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "collapsed": true,
        "id": "g9aIJbx_Leok",
        "outputId": "248f0278-59ac-4ffd-9b09-92b0ac364c85"
      },
      "outputs": [
        {
          "output_type": "stream",
          "name": "stdout",
          "text": [
            "Requirement already satisfied: SpeechRecognition in /usr/local/lib/python3.10/dist-packages (3.10.4)\n",
            "Requirement already satisfied: gtts in /usr/local/lib/python3.10/dist-packages (2.5.3)\n",
            "Collecting langdetect\n",
            "  Downloading langdetect-1.0.9.tar.gz (981 kB)\n",
            "\u001b[2K     \u001b[90m━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━\u001b[0m \u001b[32m981.5/981.5 kB\u001b[0m \u001b[31m12.7 MB/s\u001b[0m eta \u001b[36m0:00:00\u001b[0m\n",
            "\u001b[?25h  Preparing metadata (setup.py) ... \u001b[?25l\u001b[?25hdone\n",
            "Collecting pydub\n",
            "  Downloading pydub-0.25.1-py2.py3-none-any.whl.metadata (1.4 kB)\n",
            "Requirement already satisfied: streamlit in /usr/local/lib/python3.10/dist-packages (1.39.0)\n",
            "Requirement already satisfied: requests>=2.26.0 in /usr/local/lib/python3.10/dist-packages (from SpeechRecognition) (2.32.3)\n",
            "Requirement already satisfied: typing-extensions in /usr/local/lib/python3.10/dist-packages (from SpeechRecognition) (4.12.2)\n",
            "Requirement already satisfied: click<8.2,>=7.1 in /usr/local/lib/python3.10/dist-packages (from gtts) (8.1.7)\n",
            "Requirement already satisfied: six in /usr/local/lib/python3.10/dist-packages (from langdetect) (1.16.0)\n",
            "Requirement already satisfied: altair<6,>=4.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (4.2.2)\n",
            "Requirement already satisfied: blinker<2,>=1.0.0 in /usr/lib/python3/dist-packages (from streamlit) (1.4)\n",
            "Requirement already satisfied: cachetools<6,>=4.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (5.5.0)\n",
            "Requirement already satisfied: numpy<3,>=1.20 in /usr/local/lib/python3.10/dist-packages (from streamlit) (1.26.4)\n",
            "Requirement already satisfied: packaging<25,>=20 in /usr/local/lib/python3.10/dist-packages (from streamlit) (24.1)\n",
            "Requirement already satisfied: pandas<3,>=1.4.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (2.2.2)\n",
            "Requirement already satisfied: pillow<11,>=7.1.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (10.4.0)\n",
            "Requirement already satisfied: protobuf<6,>=3.20 in /usr/local/lib/python3.10/dist-packages (from streamlit) (3.20.3)\n",
            "Requirement already satisfied: pyarrow>=7.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (16.1.0)\n",
            "Requirement already satisfied: rich<14,>=10.14.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (13.8.1)\n",
            "Requirement already satisfied: tenacity<10,>=8.1.0 in /usr/local/lib/python3.10/dist-packages (from streamlit) (9.0.0)\n",
            "Requirement already satisfied: toml<2,>=0.10.1 in /usr/local/lib/python3.10/dist-packages (from streamlit) (0.10.2)\n",
            "Requirement already satisfied: gitpython!=3.1.19,<4,>=3.0.7 in /usr/local/lib/python3.10/dist-packages (from streamlit) (3.1.43)\n",
            "Requirement already satisfied: pydeck<1,>=0.8.0b4 in /usr/local/lib/python3.10/dist-packages (from streamlit) (0.9.1)\n",
            "Requirement already satisfied: tornado<7,>=6.0.3 in /usr/local/lib/python3.10/dist-packages (from streamlit) (6.3.3)\n",
            "Requirement already satisfied: watchdog<6,>=2.1.5 in /usr/local/lib/python3.10/dist-packages (from streamlit) (5.0.3)\n",
            "Requirement already satisfied: entrypoints in /usr/local/lib/python3.10/dist-packages (from altair<6,>=4.0->streamlit) (0.4)\n",
            "Requirement already satisfied: jinja2 in /usr/local/lib/python3.10/dist-packages (from altair<6,>=4.0->streamlit) (3.1.4)\n",
            "Requirement already satisfied: jsonschema>=3.0 in /usr/local/lib/python3.10/dist-packages (from altair<6,>=4.0->streamlit) (4.23.0)\n",
            "Requirement already satisfied: toolz in /usr/local/lib/python3.10/dist-packages (from altair<6,>=4.0->streamlit) (0.12.1)\n",
            "Requirement already satisfied: gitdb<5,>=4.0.1 in /usr/local/lib/python3.10/dist-packages (from gitpython!=3.1.19,<4,>=3.0.7->streamlit) (4.0.11)\n",
            "Requirement already satisfied: python-dateutil>=2.8.2 in /usr/local/lib/python3.10/dist-packages (from pandas<3,>=1.4.0->streamlit) (2.8.2)\n",
            "Requirement already satisfied: pytz>=2020.1 in /usr/local/lib/python3.10/dist-packages (from pandas<3,>=1.4.0->streamlit) (2024.2)\n",
            "Requirement already satisfied: tzdata>=2022.7 in /usr/local/lib/python3.10/dist-packages (from pandas<3,>=1.4.0->streamlit) (2024.2)\n",
            "Requirement already satisfied: charset-normalizer<4,>=2 in /usr/local/lib/python3.10/dist-packages (from requests>=2.26.0->SpeechRecognition) (3.3.2)\n",
            "Requirement already satisfied: idna<4,>=2.5 in /usr/local/lib/python3.10/dist-packages (from requests>=2.26.0->SpeechRecognition) (3.10)\n",
            "Requirement already satisfied: urllib3<3,>=1.21.1 in /usr/local/lib/python3.10/dist-packages (from requests>=2.26.0->SpeechRecognition) (2.2.3)\n",
            "Requirement already satisfied: certifi>=2017.4.17 in /usr/local/lib/python3.10/dist-packages (from requests>=2.26.0->SpeechRecognition) (2024.8.30)\n",
            "Requirement already satisfied: markdown-it-py>=2.2.0 in /usr/local/lib/python3.10/dist-packages (from rich<14,>=10.14.0->streamlit) (3.0.0)\n",
            "Requirement already satisfied: pygments<3.0.0,>=2.13.0 in /usr/local/lib/python3.10/dist-packages (from rich<14,>=10.14.0->streamlit) (2.18.0)\n",
            "Requirement already satisfied: smmap<6,>=3.0.1 in /usr/local/lib/python3.10/dist-packages (from gitdb<5,>=4.0.1->gitpython!=3.1.19,<4,>=3.0.7->streamlit) (5.0.1)\n",
            "Requirement already satisfied: MarkupSafe>=2.0 in /usr/local/lib/python3.10/dist-packages (from jinja2->altair<6,>=4.0->streamlit) (2.1.5)\n",
            "Requirement already satisfied: attrs>=22.2.0 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (24.2.0)\n",
            "Requirement already satisfied: jsonschema-specifications>=2023.03.6 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (2023.12.1)\n",
            "Requirement already satisfied: referencing>=0.28.4 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (0.35.1)\n",
            "Requirement already satisfied: rpds-py>=0.7.1 in /usr/local/lib/python3.10/dist-packages (from jsonschema>=3.0->altair<6,>=4.0->streamlit) (0.20.0)\n",
            "Requirement already satisfied: mdurl~=0.1 in /usr/local/lib/python3.10/dist-packages (from markdown-it-py>=2.2.0->rich<14,>=10.14.0->streamlit) (0.1.2)\n",
            "Downloading pydub-0.25.1-py2.py3-none-any.whl (32 kB)\n",
            "Building wheels for collected packages: langdetect\n",
            "  Building wheel for langdetect (setup.py) ... \u001b[?25l\u001b[?25hdone\n",
            "  Created wheel for langdetect: filename=langdetect-1.0.9-py3-none-any.whl size=993221 sha256=a7a75d48acccec0cac95a71d7ce3d2467c65b32364c37a332c877d1c6c7ba51b\n",
            "  Stored in directory: /root/.cache/pip/wheels/95/03/7d/59ea870c70ce4e5a370638b5462a7711ab78fba2f655d05106\n",
            "Successfully built langdetect\n",
            "Installing collected packages: pydub, langdetect\n",
            "Successfully installed langdetect-1.0.9 pydub-0.25.1\n"
          ]
        }
      ],
      "source": [
        "!pip install SpeechRecognition gtts langdetect pydub streamlit\n"
      ]
    },
    {
      "cell_type": "code",
      "source": [
        "import speech_recognition as sr\n",
        "from gtts import gTTS\n",
        "import os\n",
        "from langdetect import detect\n",
        "from pydub import AudioSegment\n",
        "from pydub.playback import play\n"
      ],
      "metadata": {
        "id": "RnKtZad5Lo-B"
      },
      "execution_count": 4,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "# Define character responses in multiple languages\n",
        "responses = {\n",
        "    'en': [\"Why are you asking that?\", \"I can't help you with that.\", \"Do you really need to know?\"],\n",
        "    'hi': [\"आप ऐसा क्यों पूछ रहे हैं?\", \"मैं आपकी मदद नहीं कर सकता।\", \"क्या आपको सच में यह जानना है?\"],\n",
        "    'ml': [\"നിങ്ങൾ അത് ചോദിക്കുന്നത് എന്തുകൊണ്ടാണ്?\", \"ഞാൻ നിങ്ങളെ സഹായിക്കാൻ കഴിയില്ല.\", \"നിങ്ങൾക്ക് ഇതു അറിയേണ്ടതുണ്ടോ?\"],\n",
        "    'ta': [\"நீங்கள் அதை ஏன் கேட்கிறீர்கள்?\", \"நான் உங்களுக்கு உதவ முடியாது.\", \"உங்களுக்கு இதை உண்மையிலே தெரிந்திருக்க வேண்டுமா?\"],\n",
        "    'kn': [\"ನೀವು ಅದು ಏಕೆ ಕೇಳುತ್ತಿದ್ದೀರಿ?\", \"ನಾನು ನಿಮಗೆ ಸಹಾಯ ಮಾಡಲು ಸಾಧ್ಯವಾಗುವುದಿಲ್ಲ.\", \"ನೀವು ಇದನ್ನು ಕೇಳಲು ಬಯಸುತ್ತೀರಾ?\"],\n",
        "    'te': [\"మీరు అదేమిటి అడుగుతున్నారో?\", \"నేను మీకు సహాయం చేయలేను.\", \"మీకు ఇదే తెలియాలి?\"]\n",
        "}\n"
      ],
      "metadata": {
        "id": "6difwd1wMalj"
      },
      "execution_count": 5,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "# Function to recognize speech from the microphone\n",
        "def recognize_speech_from_mic():\n",
        "    recognizer = sr.Recognizer()\n",
        "    with sr.Microphone() as source:\n",
        "        print(\"Listening...\")\n",
        "        audio = recognizer.listen(source)\n",
        "        try:\n",
        "            text = recognizer.recognize_google(audio)\n",
        "            print(f\"You said: {text}\")\n",
        "            return text\n",
        "        except sr.UnknownValueError:\n",
        "            print(\"Sorry, I did not understand that.\")\n",
        "            return \"\"\n",
        "        except sr.RequestError:\n",
        "            print(\"Could not request results; check your network connection.\")\n",
        "            return \"\"\n",
        "\n"
      ],
      "metadata": {
        "id": "lD-uoebXMerl"
      },
      "execution_count": 6,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "def text_to_speech(text, lang_code='en'):\n",
        "    lang_dict = {\n",
        "        'en': 'en',  # English\n",
        "        'hi': 'hi',  # Hindi\n",
        "        'ml': 'ml',  # Malayalam\n",
        "        'ta': 'ta',  # Tamil\n",
        "        'kn': 'kn',  # Kannada\n",
        "        'te': 'te'   # Telugu\n",
        "    }\n",
        "\n",
        "    lang_code = lang_dict.get(lang_code, 'en')  # Default to English if not found\n",
        "    tts = gTTS(text=text, lang=lang_code)\n",
        "    tts.save(\"response.mp3\")\n",
        "\n",
        "    # Play the audio\n",
        "    audio = AudioSegment.from_mp3(\"response.mp3\")\n",
        "    play(audio)\n"
      ],
      "metadata": {
        "id": "Oll8fzDvMiYd"
      },
      "execution_count": 7,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "# Function to generate responses based on character and detected language\n",
        "def generate_response(user_input):\n",
        "    try:\n",
        "        language = detect(user_input)\n",
        "    except Exception as e:\n",
        "        print(f\"Language detection failed: {e}\")\n",
        "        language = 'en'  # Default to English if detection fails\n",
        "\n",
        "    response = responses.get(language, responses['en'])[0]  # Fallback to English\n",
        "    return response\n"
      ],
      "metadata": {
        "id": "tNqmL1n9Mm3p"
      },
      "execution_count": 8,
      "outputs": []
    },
    {
      "cell_type": "code",
      "source": [
        "import streamlit as st\n",
        "st.title(\"Multilingual AI Voice Assistant\")\n",
        "\n",
        "if st.button(\"Speak\"):\n",
        "    user_input = recognize_speech_from_mic()\n",
        "    if user_input:\n",
        "        st.write(f\"You said: {user_input}\")\n",
        "\n",
        "        response = generate_response(user_input)\n",
        "        st.write(f\"Bot: {response}\")\n",
        "\n",
        "        # Use detected language for text-to-speech\n",
        "        lang_code = detect(user_input)  # Detect language again for TTS\n",
        "        text_to_speech(response, lang_code)\n"
      ],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/"
        },
        "id": "QSjZNFqgMuar",
        "outputId": "24a89c94-ca3c-41ca-c6ab-b7f3e1736d13"
      },
      "execution_count": 10,
      "outputs": [
        {
          "output_type": "stream",
          "name": "stderr",
          "text": [
            "2024-10-05 05:42:31.928 WARNING streamlit.runtime.scriptrunner_utils.script_run_context: Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n",
            "2024-10-05 05:42:32.057 \n",
            "  \u001b[33m\u001b[1mWarning:\u001b[0m to view this Streamlit app on a browser, run it with the following\n",
            "  command:\n",
            "\n",
            "    streamlit run /usr/local/lib/python3.10/dist-packages/colab_kernel_launcher.py [ARGUMENTS]\n",
            "2024-10-05 05:42:32.061 Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n",
            "2024-10-05 05:42:32.074 Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n",
            "2024-10-05 05:42:32.081 Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n",
            "2024-10-05 05:42:32.086 Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n",
            "2024-10-05 05:42:32.090 Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n",
            "2024-10-05 05:42:32.093 Thread 'MainThread': missing ScriptRunContext! This warning can be ignored when running in bare mode.\n"
          ]
        }
      ]
    },
    {
      "cell_type": "code",
      "source": [],
      "metadata": {
        "colab": {
          "base_uri": "https://localhost:8080/",
          "height": 408
        },
        "id": "-mrCzpM-M6OR",
        "outputId": "6d033182-fb53-4eb2-ac85-8b9350a47edb"
      },
      "execution_count": 13,
      "outputs": [
        {
          "output_type": "error",
          "ename": "AttributeError",
          "evalue": "Could not find PyAudio; check installation",
          "traceback": [
            "\u001b[0;31m---------------------------------------------------------------------------\u001b[0m",
            "\u001b[0;31mModuleNotFoundError\u001b[0m                       Traceback (most recent call last)",
            "\u001b[0;32m/usr/local/lib/python3.10/dist-packages/speech_recognition/__init__.py\u001b[0m in \u001b[0;36mget_pyaudio\u001b[0;34m()\u001b[0m\n\u001b[1;32m    107\u001b[0m         \u001b[0;32mtry\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m--> 108\u001b[0;31m             \u001b[0;32mimport\u001b[0m \u001b[0mpyaudio\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m    109\u001b[0m         \u001b[0;32mexcept\u001b[0m \u001b[0mImportError\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;31mModuleNotFoundError\u001b[0m: No module named 'pyaudio'",
            "\nDuring handling of the above exception, another exception occurred:\n",
            "\u001b[0;31mAttributeError\u001b[0m                            Traceback (most recent call last)",
            "\u001b[0;32m<ipython-input-13-d941c8ca20ed>\u001b[0m in \u001b[0;36m<cell line: 21>\u001b[0;34m()\u001b[0m\n\u001b[1;32m     19\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m     20\u001b[0m \u001b[0;31m# Run this to test\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m---> 21\u001b[0;31m \u001b[0mrecognize_speech_from_mic\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m",
            "\u001b[0;32m<ipython-input-13-d941c8ca20ed>\u001b[0m in \u001b[0;36mrecognize_speech_from_mic\u001b[0;34m()\u001b[0m\n\u001b[1;32m      4\u001b[0m \u001b[0;32mdef\u001b[0m \u001b[0mrecognize_speech_from_mic\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      5\u001b[0m     \u001b[0mrecognizer\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0msr\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mRecognizer\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m----> 6\u001b[0;31m     \u001b[0;32mwith\u001b[0m \u001b[0msr\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mMicrophone\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m \u001b[0;32mas\u001b[0m \u001b[0msource\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m      7\u001b[0m         \u001b[0mprint\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"Listening...\"\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m      8\u001b[0m         \u001b[0maudio\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mrecognizer\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mlisten\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0msource\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;32m/usr/local/lib/python3.10/dist-packages/speech_recognition/__init__.py\u001b[0m in \u001b[0;36m__init__\u001b[0;34m(self, device_index, sample_rate, chunk_size)\u001b[0m\n\u001b[1;32m     78\u001b[0m \u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m     79\u001b[0m         \u001b[0;31m# set up PyAudio\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m---> 80\u001b[0;31m         \u001b[0mself\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mpyaudio_module\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mself\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mget_pyaudio\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m     81\u001b[0m         \u001b[0maudio\u001b[0m \u001b[0;34m=\u001b[0m \u001b[0mself\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mpyaudio_module\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mPyAudio\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m     82\u001b[0m         \u001b[0;32mtry\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;32m/usr/local/lib/python3.10/dist-packages/speech_recognition/__init__.py\u001b[0m in \u001b[0;36mget_pyaudio\u001b[0;34m()\u001b[0m\n\u001b[1;32m    108\u001b[0m             \u001b[0;32mimport\u001b[0m \u001b[0mpyaudio\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m    109\u001b[0m         \u001b[0;32mexcept\u001b[0m \u001b[0mImportError\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0;32m--> 110\u001b[0;31m             \u001b[0;32mraise\u001b[0m \u001b[0mAttributeError\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"Could not find PyAudio; check installation\"\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[0m\u001b[1;32m    111\u001b[0m         \u001b[0;32mfrom\u001b[0m \u001b[0mdistutils\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0mversion\u001b[0m \u001b[0;32mimport\u001b[0m \u001b[0mLooseVersion\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n\u001b[1;32m    112\u001b[0m         \u001b[0;32mif\u001b[0m \u001b[0mLooseVersion\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0mpyaudio\u001b[0m\u001b[0;34m.\u001b[0m\u001b[0m__version__\u001b[0m\u001b[0;34m)\u001b[0m \u001b[0;34m<\u001b[0m \u001b[0mLooseVersion\u001b[0m\u001b[0;34m(\u001b[0m\u001b[0;34m\"0.2.11\"\u001b[0m\u001b[0;34m)\u001b[0m\u001b[0;34m:\u001b[0m\u001b[0;34m\u001b[0m\u001b[0;34m\u001b[0m\u001b[0m\n",
            "\u001b[0;31mAttributeError\u001b[0m: Could not find PyAudio; check installation"
          ]
        }
      ]
    }
  ]
}
