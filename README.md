# Import the necessary libraries
import boto3

# Set up the client for the Amazon Advertising API
client = boto3.client('advertising')

# Set the parameters for the search query
params = {
    'startIndex': 0,
    'count': 100,
    'sort': 'relevance',
    'sortBy': 'searchVolume'
}

# Use the 'search' method of the client to find the most searched keywords
response = client.search(params)

# Print the top keywords found in the search
for keyword in response['keywords']:
    print(keyword['keyword'])

