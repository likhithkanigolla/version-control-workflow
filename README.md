### **Versioning Structure**
Semantic versioning uses the format:  
```
MAJOR.MINOR.PATCH
```

1. **MAJOR**: Breaking changes.
2. **MINOR**: New features that are backward-compatible.
3. **PATCH**: Bug fixes or other backward-compatible changes.

---

### **Commit Message Types and Their Effect on Version Numbers**

| **Commit Type**         | **Example Commit Message**                        | **Version Change**           | **Reason**                                         |
|--------------------------|--------------------------------------------------|-------------------------------|---------------------------------------------------|
| **feat** (Feature)       | `feat(auth): add user login functionality`       | **MINOR**                     | Adds a new feature in a backward-compatible way.  |
| **fix** (Bug Fix)        | `fix(ui): resolve login button alignment issue`  | **PATCH**                     | Fixes an issue without breaking existing features.|
| **docs** (Documentation) | `docs(api): add API endpoint usage examples`     | No Version Change             | Does not affect code behavior.                   |
| **style** (Styling)      | `style(ui): update CSS for header alignment`     | No Version Change             | Only changes style; no functional impact.         |
| **refactor**             | `refactor(auth): simplify token generation logic`| No Version Change             | No functional or feature impact; internal change. |
| **perf** (Performance)   | `perf(db): optimize query for fetching users`    | **PATCH**                     | Improves performance without changing functionality.|
| **test** (Testing)       | `test(api): add tests for user login endpoint`   | No Version Change             | Testing-only changes.                            |
| **chore** (Maintenance)  | `chore(deps): update npm packages`              | No Version Change             | Maintenance tasks that don’t affect functionality.|
| **BREAKING CHANGE**      | `feat(auth): migrate to OAuth 2.0 authentication`| **MAJOR**                     | Introduces a change that breaks compatibility.    |

---

### **Commit Messages and Their Impacts**
#### **1. MAJOR Version Changes**
   - Triggered when you include a **breaking change**.  
   - Use `BREAKING CHANGE:` in the commit footer.
   - Example:
     ```
     feat(auth): migrate to OAuth 2.0 authentication

     BREAKING CHANGE: The user login endpoint now requires OAuth 2.0 tokens instead of API keys.
     ```
   - **Effect**: Version changes from `1.2.3` → `2.0.0`.

---

#### **2. MINOR Version Changes**
   - Triggered by `feat` commits (features).
   - Adds functionality in a backward-compatible manner.
   - Example:
     ```
     feat(api): add support for password reset functionality
     ```
   - **Effect**: Version changes from `1.2.3` → `1.3.0`.

---

#### **3. PATCH Version Changes**
   - Triggered by `fix` or `perf` commits.
   - Fixes bugs or improves performance without breaking or adding new features.
   - Example:
     ```
     fix(db): resolve timeout issue during bulk user creation
     ```
   - **Effect**: Version changes from `1.2.3` → `1.2.4`.

---

#### **4. No Version Change**
   - Triggered by `docs`, `style`, `test`, `refactor`, or `chore` commits (no functional changes).
   - Example:
     ```
     docs(readme): update setup instructions for contributors
     ```
   - **Effect**: Version remains the same, e.g., `1.2.3`.

---

### **Quick Reference for Teams**

1. **If you're adding a feature:**  
   Use `feat` → Bumps **MINOR** version.  
   Example: `feat(ui): add dark mode support`

2. **If you're fixing a bug:**  
   Use `fix` → Bumps **PATCH** version.  
   Example: `fix(auth): resolve incorrect password validation`

3. **If you're making a breaking change:**  
   Use `feat` or `fix` with `BREAKING CHANGE` in the footer → Bumps **MAJOR** version.  
   Example:
   ```
   feat(auth): switch to token-based authentication

   BREAKING CHANGE: All API clients must now use token-based headers.
   ```

4. **If you're improving performance:**  
   Use `perf` → Bumps **PATCH** version.  
   Example: `perf(api): improve response time for search queries`

5. **If you're documenting or cleaning up code:**  
   Use `docs`, `style`, `test`, `refactor`, or `chore` → No version change.  
   Example: `docs(api): add detailed usage instructions for developers`
