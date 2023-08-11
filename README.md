# LeetcodeScraper Documentation

The `LeetcodeScraper` is a Python class designed to scrape user data from the LeetCode platform using GraphQL queries. This documentation provides an overview of the class and its methods, explaining how to use it to fetch various data related to user profiles and global rankings on LeetCode.


## Introduction

The `LeetcodeScraper` class is designed to interact with the LeetCode platform using GraphQL queries. It provides methods for fetching various user-related data, including user profiles and global ranking information.

## Getting Started

To use the `LeetcodeScraper` class, you need to import the necessary libraries and create an instance of the class. Here's an example of how to set up the scraper:

```python
from leetcode_scraper import LeetcodeScraper

scraper = LeetcodeScraper()
```

## Methods

### `scrape_user_profile(username)`

This method fetches various details related to a user's public profile on LeetCode.

- `username` (str): The username of the LeetCode user.

Returns a dictionary containing the user's public profile data, including contest badges, social media links, user avatar, reputation, solution counts, and more.

### `_scrape_single_global_ranking_page(page_num, only_user_details=True)`

This method fetches user details from a single page of the LeetCode global ranking.

- `page_num` (int): The page number of the global ranking to fetch.
- `only_user_details` (bool): If `True`, fetch only user details; if `False`, fetch global ranking metadata as well.

Returns a list of dictionaries containing user details from the specified global ranking page.

### `scrape_all_global_ranking_users()`

This method scrapes user details from all pages of the LeetCode global ranking.

Returns a dictionary with the following information:
- `total_global_ranking_users_present`: Total number of users present in the global ranking.
- `total_global_ranking_users_scraped`: Total number of users scraped by the scraper.
- `total_global_ranking_pages`: Total number of pages in the global ranking.
- `all_global_ranking_users`: A list of dictionaries containing basic user details from all global ranking pages.

## Usage Examples

### Fetching User Profile Data

```python
scraper = LeetcodeScraper()
username = 'example_username'
profile_data = scraper.scrape_user_profile(username)
print(profile_data)
```

### Fetching Global Ranking Users

```python
scraper = LeetcodeScraper()
global_ranking_data = scraper.scrape_all_global_ranking_users()
print(global_ranking_data)
```

## Important Notes

- This scraper interacts with LeetCode's GraphQL API. Be mindful of the platform's usage policies and rate limits.
- The use of multithreading is employed to improve performance. Adjust the `max_workers` parameter in the `ThreadPoolExecutor` according to your requirements.

Please ensure you respect LeetCode's terms of use and scraping guidelines while using this scraper.

---

Feel free to integrate the `LeetcodeScraper` class into your projects to fetch LeetCode user data and global ranking information. If you encounter any issues or need further assistance, please don't hesitate to reach out.
