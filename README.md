import requests
from datetime import datetime
import json
from typing import List, Dict
 
class SpringOutingPlanner:
    def __init__(self):
        self.weather_api_key = "your_weather_api_key"  # 替换为实际天气API密钥
        self.attractions = [
            {"name": "颐和园", "location": "北京", "best_season": "春季", "rating": 4.8},
            {"name": "西湖", "location": "杭州", "best_season": "春季", "rating": 4.9},
            {"name": "武汉大学樱花", "location": "武汉", "best_season": "春季", "rating": 4.7},
            {"name": "婺源油菜花", "location": "江西", "best_season": "春季", "rating": 4.6},
            {"name": "扬州瘦西湖", "location": "扬州", "best_season": "春季", "rating": 4.5}
        ]
    
    def recommend_attractions(self, location: str = None) -> List[Dict]:
        """推荐适合春游的景点"""
        recommendations = []
        for attr in self.attractions:
            if attr["best_season"] == "春季":
                if location is None or location.lower() in attr["location"].lower():
                    recommendations.append(attr)
