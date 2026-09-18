# Data Dictionary

This folder contains the raw datasets used in the AtliQ Grands hospitality analysis. All files are CSVs and are read directly by `notebook/hospitality_project.ipynb`.

## `dim_hotels.csv`
Hotel property master data.

| Column | Description |
|---|---|
| `property_id` | Unique identifier for each hotel property |
| `property_name` | Name of the hotel |
| `category` | Hotel category/star rating |
| `city` | City the property is located in |

## `dim_date.csv`
Calendar dimension used to classify and merge booking dates.

| Column | Description |
|---|---|
| `date` | Calendar date |
| `mmm yy` | Month and year (e.g. "Jun 22") |
| `week no` | Week number |
| `day_type` | Weekday or Weekend |

## `dim_rooms.csv`
Room category and class mapping.

| Column | Description |
|---|---|
| `room_id` | Room category code (e.g. RT1, RT2) |
| `room_class` | Room class label (e.g. Standard, Elite, Premium, Luxury) |

## `fact_bookings.csv`
Individual, booking-level transaction data — the most granular table.

| Column | Description |
|---|---|
| `booking_id` | Unique booking identifier |
| `property_id` | Hotel property the booking belongs to |
| `booking_date` | Date the booking was made |
| `check_in_date` | Guest check-in date |
| `checkout_date` | Guest checkout date |
| `no_guests` | Number of guests on the booking |
| `room_category` | Room category booked |
| `booking_platform` | Platform the booking was made through (e.g. direct, online travel agency) |
| `ratings_given` | Guest rating for the stay, if provided |
| `booking_status` | Status of the booking (e.g. checked out, cancelled, no show) |
| `revenue_generated` | Revenue expected from the booking |
| `revenue_realized` | Actual revenue collected |

## `fact_aggregated_bookings.csv`
Daily, property-level aggregated booking and capacity data.

| Column | Description |
|---|---|
| `property_id` | Hotel property |
| `check_in_date` | Date of stay |
| `room_category` | Room category |
| `successful_bookings` | Number of successful bookings for that day/room category |
| `capacity` | Total available room capacity for that day/room category |

## `new_data_august.csv`
Additional booking data for August, appended to the aggregated bookings dataset to extend the analysis period. Same structure as `fact_aggregated_bookings.csv`.

## Data Quality Notes

The raw files contain known issues addressed during cleaning (see the notebook and main README for details):
- Some `no_guests` values in `fact_bookings.csv` are zero or negative (invalid) and were removed
- `revenue_generated` and `revenue_realized` contain statistical outliers, filtered using the 3-standard-deviation rule
- `capacity` in `fact_aggregated_bookings.csv` has missing values, imputed using the median
