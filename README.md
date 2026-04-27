# ==========================================
# Project: IdeaS
# Description:
# A place where raw ideas are forged into polished software
# through experimentation, learning, and continuous improvement.
# ==========================================


# ---------- main.py ----------
"""
Main entry point for IdeaSmith.
"""

from core.experiment import ExperimentForge
from core.improvement import ImprovementEngine


def run():
    print("🔥 IdeaSmith Activated")
    print("🧪 Experimentation | 📚 Learning | 🔄 Continuous Improvement\n")

    forge = ExperimentForge()
    improve = ImprovementEngine()

    ideas = ["automation", "optimization", "analytics"]

    # Turn raw ideas into prototypes
    prototypes = forge.forge(ideas)
    print("⚙️ Prototypes:", prototypes)

    # Improve system metrics
    metrics = {"quality": 0.7, "performance": 0.6}
    print("📈 Improved Metrics:", improve.refine(metrics))

    # Learning cycle
    data = [2, 4, 6, 8]
    print("🧠 Learning Output:", forge.learn(lambda x: x ** 2, data))


if __name__ == "__main__":
    run()


# ---------- core/experiment.py ----------
"""
Experimentation and idea-forging module.
"""

class ExperimentForge:
    """Transforms raw ideas into working prototypes."""

    def forge(self, ideas):
        """Create prototype names from raw ideas."""
        return [f"{idea}_prototype" for idea in ideas]

    def learn(self, func, dataset):
        """Apply a learning transformation."""
        return [func(x) for x in dataset]


# ---------- core/improvement.py ----------
"""
Continuous improvement and refinement module.
"""

class ImprovementEngine:
    """Handles iterative refinement of system metrics."""

    def refine(self, metrics, rate=0.1):
        """Improve metrics gradually."""
        return {
            key: round(value * (1 + rate), 3)
            for key, value in metrics.items()
        }

    def evaluate(self, metrics):
        """Evaluate overall improvement score."""
        if not metrics:
            return 0
        return round(sum(metrics.values()) / len(metrics), 3)


# ---------- tests/test_experiment.py ----------
"""
Tests for ExperimentForge.
"""

from core.experiment import ExperimentForge

def test_forge():
    forge = ExperimentForge()
    result = forge.forge(["test"])
    assert "test_prototype" in result

def test_learn():
    forge = ExperimentForge()
    assert forge.learn(lambda x: x + 1, [1, 2]) == [2, 3]


# ---------- tests/test_improvement.py ----------
"""
Tests for ImprovementEngine.
"""

from core.improvement import ImprovementEngine

def test_refine():
    engine = ImprovementEngine()
    improved = engine.refine({"quality": 1.0})
    assert improved["quality"] > 1.0
