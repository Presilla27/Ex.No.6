## Ex.No.6
## Development of Python Code Compatible with Multiple AI Tools

## Name: Presilla K
## Reg No: 212223050038

## Aim

To develop Python code that integrates with multiple AI tools by reading data from different file formats such as CSV and JSON, converting them into a standardized structure, and using the structured data as input prompts for AI tools like ChatGPT to generate meaningful insights.

This experiment demonstrates the Persona Pattern, where a single interface processes multiple input formats and produces consistent output suitable for AI interaction.

## Tool Used

Python Programming Language
ChatGPT AI Tool

Python is used to process data from different file formats.
ChatGPT is used to analyze structured data using prompts.

## Introduction

Artificial Intelligence tools such as ChatGPT require structured input to generate accurate results. Data can exist in different formats such as CSV or JSON. To ensure compatibility with multiple AI tools, the input data must be standardized.

The Persona Pattern helps create a single interface that accepts multiple input formats and converts them into a common structure.

In this experiment, a Python function reads CSV and JSON files and converts them into a list of dictionaries format. This standardized format can be easily used as input prompt for AI tools.

This approach improves:

flexibility
reusability
compatibility
scalability
Persona Pattern Concept

Persona Pattern means creating a single adaptable interface that works with multiple tools or data formats.

Instead of writing separate programs for CSV and JSON, one function processes both formats and produces the same structured output.

This makes the system efficient and easy to integrate with AI tools.
## Prompt Used to Generate the Python Code

Act as an expert Python developer specialized in Artificial Intelligence integration. Write a Python program that connects with multiple AI tools using APIs and automates the process of sending prompts and receiving responses. The program should integrate at least two AI tools such as ChatGPT API and Gemini API. Use the Python requests library to send HTTP POST requests to the APIs.

The program should use the same prompt input for both AI tools: "Analyze the benefits of renewable energy and provide key insights." Create separate functions to send the prompt to each AI API and retrieve the generated responses. The responses returned by both AI tools should then be compared to identify common keywords such as environment, sustainability, or renewable energy.

Based on the comparison, the program should generate actionable insights that summarize common ideas found in both AI outputs. Structure the program clearly with functions for API communication and output comparison. Print the responses obtained from each AI tool and display the final insights generated from comparing the outputs.

The code should be properly structured, readable, and suitable for demonstrating integration of multiple AI tools using Python APIs.

## Python Code Implementation
import csv
import json
import os

def read_file_as_dicts(file_path):

    if not os.path.exists(file_path):
        raise FileNotFoundError(f"File '{file_path}' not found.")

    extension = os.path.splitext(file_path)[1].lower()

    if extension == ".csv":
        with open(file_path, mode="r", encoding="utf-8") as f:
            reader = csv.DictReader(f)
            data = [row for row in reader]
        return data

    elif extension == ".json":
        with open(file_path, mode="r", encoding="utf-8") as f:
            data = json.load(f)
            if isinstance(data, dict):
                data = [data]
        return data

    else:
        raise ValueError("Unsupported file format")

if __name__ == "__main__":
    csv_data = read_file_as_dicts("data.csv")
    json_data = read_file_as_dicts("data.json")

    print(csv_data)
    print(json_data)
Input Files
CSV File (data.csv)

name,age,city
Hema,21,Chennai
Arun,23,Bangalore

JSON File (data.json)

[
{"name":"Hema","age":21,"city":"Chennai"},
{"name":"Arun","age":23,"city":"Bangalore"}
]

How the Python Code Works

Step 1
The program checks whether the file exists.

Step 2
It identifies the file format (CSV or JSON).

Step 3
If the file is CSV, the csv.DictReader function converts each row into dictionary format.

Step 4
If the file is JSON, json.load converts JSON data into dictionary format.

Step 5
Both file formats are converted into a common structure called list of dictionaries.

Example output format:

[
{"name":"Hema","age":"21","city":"Chennai"},
{"name":"Arun","age":"23","city":"Bangalore"}
]

Flow of Persona Pattern

Input File (.csv or .json)

File format identified

Content converted into dictionary format

Output standardized as list of dictionaries

Structured data given as prompt input to AI tool

AI generates meaningful response

Prompt Used in ChatGPT (Input to AI)

Analyze the following dataset and provide summary.
Find the average age and list the cities present in the dataset.

Data:
[
{"name":"Hema","age":21,"city":"Chennai"},
{"name":"Arun","age":23,"city":"Bangalore"}
]

How AI Interprets the Prompt

ChatGPT reads the structured data provided in dictionary format.

The AI understands:

name field represents person name
age field represents numerical value
city field represents location

AI processes the data and performs analysis such as identifying unique cities and calculating average age.

Output Generated by AI

Summary:
The dataset contains information about two individuals named Hema and Arun.

Average Age:
(21 + 23) / 2 = 22

Cities Present:
Chennai
Bangalore

The data shows individuals from two different cities with an average age of 22.

How Persona Pattern Helps AI Integration

Single function handles multiple file formats.

Output format remains same for CSV and JSON.

Same prompt structure can be used for different AI tools.

Improves efficiency and reduces need for multiple code implementations.

Easy to extend for other formats such as XML or Excel.

## Advantages

Reduces complexity in handling multiple data formats.

Provides consistent input format for AI tools.

Improves automation of data analysis.

Reusable and scalable code design.

Supports integration with multiple AI platforms.

## Result

Python code successfully reads CSV and JSON files and converts them into standardized list of dictionaries format.

The structured data is used as input prompt for ChatGPT, which generates meaningful analysis.

Persona Pattern ensures compatibility with multiple AI tools.

## Conclusion

The experiment demonstrates how Python can be used to standardize data from multiple formats and integrate with AI tools using prompts.

Persona Pattern provides a unified interface that simplifies AI interaction.

Structured prompts help AI models understand data effectively and generate accurate insights.

Thus, the integration of Python with AI tools improves automation, flexibility, and efficiency in data processing.

