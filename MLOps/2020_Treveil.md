# Introducing MLOps

(2020)
by Mark Treveil, Nicolas Omont, Clément Stenac, Kenji Lefevre, Du Phan, Joachim Zentici, Adrien Lavoillotte, Makoto Miyazaki, Lynn Heidmann

## I - What and Why

MLOps exists because machine learning systems are not software systems. Software code, once shipped, sits still. A model is made of _code plus data_, and data never stops moving. That single asymmetry is what makes MLOps a distinct discipline rather than a rebranding of DevOps. 

### Key Concepts

- **Why the interest exploded.** Companies had _many_ models in production simultaneously. One model is a project you can babysit. Fifty models is an operations problem, and managing them by hand becomes unfeasible.
- **There are two main challenges behind MLOps.** The first is related to the data itself: data can change over time, meaning that a model's performance may also change after deployment. The second is related to the people and processes involved. Data scientists are not always trained in areas such as software testing, version control, CI/CD, or production reliability. MLOps helps address both problems by providing processes and tools for monitoring and maintaining models while also bringing more engineering discipline to the machine learning lifecycle.
- **MLOps has a lot in common with DevOps, but there are important differences.** Both emphasize automation, collaboration between teams, testing, and reliable deployment processes. The main difference is that traditional software usually operates with relatively stable code, while ML systems depend heavily on data that can continuously change. A software unit test may have a clear pass or fail result, while model performance is often more dependent on the data it is evaluated on. A model that performs well today may not perform equally well in a different environment or with a different population.
- **There are more components that need to be versioned in an ML system.** In a typical software project, versioning the code is usually the main focus. For machine learning, reproducing a model may also require the training data, features, hyperparameters, trained model artifact, and the environment used during training. If any of these components change, it may be difficult to reproduce the same result. This makes experiment tracking and lineage particularly important in MLOps.
- **One of the main goals of MLOps is reducing risk.** Deploying models without the right processes can create problems with model quality, reliability, and continuity. In some situations, the impact can go beyond technical issues. For example, a model producing biased predictions could create regulatory or reputational risks for the company. This means that MLOps is not only about making deployment easier—it is also about making sure models can be operated responsibly.
- **Deployment is not the end of the machine learning lifecycle.** Once a model is in production, it still needs to be monitored and maintained. Another important point is understanding where and how each model is being used. Knowing which teams or systems depend on a model becomes particularly important when making changes or deciding to retire it, since a model can have downstream dependencies that are not immediately obvious.
- **MLOps usually involves several different functions.** Data scientists, data engineers, ML architects, software engineers, domain experts, and risk or compliance teams can all contribute to different parts of the lifecycle.
- **MLOps maturity can be developed gradually.** A first version of a model does not necessarily need a complete and sophisticated CI/CD pipeline. What seems more important is gradually improving the process with each deployment. A practical starting point could include versioning experiments and models, comparing a new model with the current one before promoting it, scheduling performance monitoring, and adding basic sanity checks to predictions.
- **Transparency is another important part of MLOps.** Teams should be able to understand what a model does, which data was used to train it, who approved it, and when it was last updated. In regulated industries, this may be necessary for audits and compliance. Even outside those environments, having this information makes it much easier to investigate problems and explain model decisions to stakeholders when something goes wrong.

## II - How

4. Developing Models

5. Preparing for Production

6. Deploying to Production

### 7. Monitoring and Feedback Loop

A machine learning model is not a finished product at deployment — it is a decaying asset. The moment a model goes live, the world it was trained on begins to drift away from the world it is scoring, and this degradation happens silently unless it is deliberately measured. Chapter 7 argues that monitoring (at both the resource and performance levels) plus a structured feedback loop is what turns a one-off model into a sustainable production system. 

The real question is never _whether_ to retrain, but _when_ — and that "when" is a business decision balancing the cost of the retraining pipeline against the value of the performance recovered.

- **Treat monitoring as part of the deliverable.** A model without metrics, thresholds, and an alert owner is not production-ready, regardless of its offline scores.
- **Use ground truth where you can, drift detection where you can't** — and ideally both, with drift as the fast early warning and ground truth as the slower confirmation.
- **Instrument for logging from day one.** Retraining requires that predictions, inputs, model version, and eventual outcomes were captured and joinable. This is far harder to retrofit than to design in.
- **Make retraining a governed, versioned process.** Validate the candidate against the incumbent (shadow scoring, champion/challenger, A/B testing) before promotion. Retraining on drifted data is not automatically an improvement.
- **Tie thresholds to business impact.** The alert that matters is the one that fires when revenue, risk, or user experience is measurably affected — not when a p-value crosses 0.05 on a feature nobody uses.

