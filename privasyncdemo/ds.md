# DATA_STRUCTURE_MODELS.md

# PrivAsync Frontend Data Models


---

# Team 1 - Authentication Module

## User

```ts
export interface User {
  id: string;

  name: string;

  email: string;

  role: "USER" | "ADMIN";

  organization?: string;

  isVerified: boolean;

  createdAt: string;

  lastLogin?: string;
}
```

## Signup Request

```ts
export interface SignupForm {
  name: string;

  email: string;

  organization: string;

  password: string;

  confirmPassword: string;
}
```

## OTP Verification

```ts
export interface OTPVerification {
  email: string;

  otp: string;
}
```

---

# Team 2 - User Dashboard

## Dashboard Stats

```ts
export interface UserDashboardStats {
  totalTrainings: number;

  activeTrainings: number;

  completedTrainings: number;

  contributedRounds: number;
}
```

## Activity Item

```ts
export interface Activity {
  id: string;

  title: string;

  description: string;

  timestamp: string;
}
```

---

# Team 3 - Admin Dashboard

## Admin Dashboard Stats

```ts
export interface AdminDashboardStats {
  totalUsers: number;

  activeUsers: number;

  activeTrainings: number;

  completedTrainings: number;

}
```

## Chart Data



---

# Team 4 - User Model Training

## Dataset

```ts
export interface Dataset {
  id: string;

  name: string;

  description: string;

  records: number;

  size: string;
}
```

## Model Configuration

```ts
export interface ModelConfig {
  modelName: string;

  epochs: number;

  batchSize: number;

  learningRate: number;

  optimizer: string;
}
```

## Training Job

```ts
export interface TrainingJob {
  id: string;

  name: string;

  datasetName: string;

  status:
    | "PENDING"
    | "RUNNING"
    | "COMPLETED"
    | "FAILED";

  progress: number;

  currentRound: number;

  totalRounds: number;

  createdAt: string;
}
```

---

# Team 5 - Admin Training Monitoring & Model Distribution

## Training Round

```ts
export interface TrainingRound {
  roundNumber: number;

  status:
    | "PENDING"
    | "RUNNING"
    | "COMPLETED";

  participants: number;

  accuracy?: number;

  loss?: number;
}
```

## Model Distribution

```ts
export interface ModelDistribution {
  id: string;

  modelVersion: string;

  distributedAt: string;

  targetClients: number;

  successfulClients: number;
}
```

## Training Monitor

```ts
export interface TrainingMonitor {
  trainingId: string;

  trainingName: string;

  activeParticipants: number;

  currentRound: number;

  totalRounds: number;

  status: string;
}
```

---

# Team 6 - Global Context Module

## Auth Context State

```ts
export interface AuthState {
  isLoggedIn: boolean;

  user: User | null;
}
```

## Loader Context State

```ts
export interface LoaderState {
  isLoading: boolean;
}
```


---

# Team 7 - Notification Center

## Notification

```ts
export interface Notification {
  id: string;

  title: string;

  message: string;

  type:
    | "INFO"
    | "SUCCESS"
    | "WARNING"
    | "ERROR";

  isRead: boolean;

  createdAt: string;
}
```

---

# Team 8 - Landing Page

## Feature Item

```ts
export interface Feature {
  id: string;

  title: string;

  description: string;

  icon: string;
}
```

## Team Member

```ts
export interface TeamMember {
  name: string;

  role: string;

  avatar: string;
}
```


---

# Shared Status Types

```ts
export type TrainingStatus =
  | "PENDING"
  | "RUNNING"
  | "COMPLETED"
  | "FAILED";
```

```ts
export type UserRole =
  | "USER"
  | "ADMIN";
```

---

# Important

All UI mock data should follow these interfaces.

Backend APIs will later be designed around these contracts to minimize frontend refactoring.
