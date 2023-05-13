# python_function_openai_api_call


```
####################
# Call API Function
####################

def call_openai_chat_api(this_input, select_model=3):
    """
    Requires:
      pip install openai
      import openai
      api key from openai, included in subscription:
      https://platform.openai.com/account/api-keys

    Chat type query to openAI:
    pecify Model, default is "gpt-3.5-turbo"
    user input-2 selects which model to use: 3, 4

    Sample use:

    this_input = "Hello."
    select_model = 3

    call_openai_chat_api(this_input, select_model=3)
    """

    if select_model == 4:
        this_model = "gpt-4"

    elif select_model == 3:
        this_model = "gpt-3.5-turbo"

    ## Hit API
    completion = openai.ChatCompletion.create(model=this_model, messages=[{"role": "user", "content": this_input}])

    # Terminal Inspection for Examination (optional)
    # print(completion)

    ## Results (slicing into the json object output)
    results = completion.choices[0].message.content
    
    return results

```
