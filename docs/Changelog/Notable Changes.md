---
id: Changelog.Notable Changes
title: Notable Changes
---
# Notable Changes
```markdown
# Changelog

## Notable Changes

This section outlines significant updates, improvements, and fixes introduced in the repository. Below are key details for developers and users to adapt their workflows.

---

### Configuration Parameter Updates

- **`use_time_based_weights` (default: `False`)**  
  Time-based weighting logic can now be explicitly disabled by setting this parameter to `false`. This provides finer control over scheduling or prioritization algorithms.  

  Example configuration snippet:
  ```yaml
  agent:
    use_time_based_weights: false
  ```

- **`time_based_multipliers` (default: `{}`)**  
  A new dictionary parameter for defining custom multipliers when time-based weighting is enabled. Configure thresholds and scaling factors here.  

---

### Documentation Updates

- **PR #133**: Fixed docstring in `_register_connection` method to reflect the correct `config_dic` parameter (replacing outdated multi-parameter documentation). Ensures API documentation aligns with implementation.  
- **Grammar and Clarity Improvements**: Revised documentation for consistency and readability across configuration guides.  

---

### Error Handling Improvements
- Enhanced validation and debugging tools for configuration files. Errors now include contextual messages to pinpoint issues like malformed fields or invalid parameter types.

---

### Additional Notes

> [!NOTE]
> - **UTF-8 Encoding**: Always save agent configuration files with UTF-8 encoding to avoid parsing errors.  
> - **Disabling Time-Based Weights**: Set `use_time_based_weights: false` to bypass time-based logic entirely.  

---

### Breaking Changes
**None.** All updates are backward-compatible. Existing configurations will continue to function as before.

---

### Summary
- Use `time_based_multipliers` to customize time-based weighting when enabled.  
- Validate configurations using improved error messages for faster troubleshooting.  
- Ensure UTF-8 encoding for configuration files to maintain compatibility.  
```
