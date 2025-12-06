# Optibus Configuration Recommendations - Metropoline Holon

## PRIORITY 1 - Critical Improvements (Implement Immediately)

### 1. Deadhead Limitation
**Status**: NOT CURRENTLY ACTIVE
**Priority**: CRITICAL
**Estimated Impact**: ₪8,000-₪12,000/day savings

```yaml
preference: deadhead_limitation
max_deadhead_percentage: 15
penalty: 1000
restricted: true
```

### 2. Driver Meal Break
**Status**: NOT CURRENTLY ACTIVE
**Priority**: CRITICAL (Regulatory Compliance)

```yaml
preference: driver_meal_break
min_duty_length_for_break: "08:00"
required_break_length: "00:30"
break_window_start: "03:00"
break_window_end: "06:00"
penalty: 5000
restricted: true
```

### 3. Split Break Definition
**Status**: NOT CURRENTLY ACTIVE
**Priority**: HIGH

```yaml
preference: split_break_definition
min_split_break_length: "02:00"
max_split_break_length: "04:00"
min_work_before_split: "03:30"
min_work_after_split: "03:30"
penalty: 100
```

## PRIORITY 2 - Important Improvements

### 4. Travel Time Limitation
**Estimated Impact**: ₪2,000-₪4,000/day

```yaml
max_travel_time: "00:45"
penalty: 200
restricted: false
```

### 5. Block Limitation
```yaml
max_block_duration: "18:00"
min_block_duration: "06:00"
penalty: 500
```

### 6. Piece Work Limitation
```yaml
max_piece_duration: "05:00"
min_piece_duration: "02:00"
penalty: 300
```

---

## CURRENTLY ACTIVE SETTINGS

### Current Cost Model
```yaml
driver_daily_fixed_cost: 120
hourly_wage: 40
vehicle_daily_fixed_cost: 200
distance_unit_cost: 6
```

### Current Split Duty Settings
```yaml
min_split_piece_length: "03:00"
split_time_compensation: "01:00"
max_split_count_per_duty: 1
```

### Current DEEP Settings
```yaml
vip_version: 3
advanced_vehicle_optimization: true
allow_end_of_day_depot_replacements: true
attempt_enrich_with_deadhead: true
multiple_enabled: true
min_spread: 420
max_accumulated_time_between_pieces: 300
```

---

## IMPLEMENTATION NOTES

For Codex to generate proper Optibus configuration:
1. Review all Priority 1 recommendations
2. Generate Python/YAML code compatible with Optibus API
3. Include proper error handling and validation
4. Provide copy-paste ready configuration
