# cognitive
cognitive_context_engine/context_model.py
Jessie OS - Cognitive Context Engine

class UserContext:
    def __init__(self):
        self.behavior_history = []
        self.emotional_state = None
        self.goals = []

    def update_behavior(self, action):
        self.behavior_history.append(action)

    def set_emotional_state(self, state):
        self.emotional_state = state

    def add_goal(self, goal):
        self.goals.append(goal)

    def summarize_context(self):
        return {
            "last_action": self.behavior_history[-1] if self.behavior_history else None,
            "emotion": self.emotional_state,
            "active_goals": self.goals[-3:] if self.goals else []
        }
