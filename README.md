import openai
openai.api_key = 'your api Key'

def generate_blog_post(paragraph_topic):
    response = openai.completion.create(
        model="gpt-3.5-turbo-instruct",
        prompt = f'write paragraph about the following topic.{paragraph_topic}',
        max_tokens = 400,
        temperature = 0.3,
    )
    return response.choices[0].text
print(generate_blog_post('Why NYC is better than your city.'))
