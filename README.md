# Bidirectional ClickHouse & Flat File Data Ingestion Tool

Author: Aastha Gupta

## Overview

This web application facilitates data transfer between ClickHouse databases and flat files with a user-friendly interface. It supports bidirectional data flow, JWT token-based authentication, custom column selection, and provides detailed progress and completion reports.

## Features

### Core Features
- **Bidirectional Data Flow**: Transfer data from ClickHouse to flat files and vice versa
- **Source/Target Selection**: Clear UI for choosing data source and target
- **ClickHouse Integration**:
  - Connection configuration (host, port, database, user)
  - JWT token-based authentication
  - Table schema discovery
- **Flat File Integration**:
  - Local file selection
  - Delimiter configuration
  - Schema inference
- **Column Selection**: Choose specific columns to transfer
- **Progress Reporting**: Real-time status updates and completion metrics
- **Error Handling**: User-friendly error messages for various failure scenarios

### Enhanced Features
- **Data Preview**: View the first 100 records before starting ingestion
- **Progress Bar**: Visual indicator of ingestion progress
- **Multi-Table Join**: (Bonus) Join multiple ClickHouse tables with custom conditions

## Technology Stack

### Backend
- Go (using official ClickHouse Go client)
- RESTful API endpoints for frontend communicatio
### ClickHouse to Flat File

1. Select "ClickHouse" as Source and "Flat File" as Target
2. Enter ClickHouse connection details:
   - Host (e.g., localhost)
   - Port (e.g., 8123)
   - Database name
   - Username
   - JWT token
3. Click "Connect" and select a table from the dropdown
4. Choose the columns to export
5. Configure flat file settings:
   - Output file path
   - Delimiter character
6. Click "Preview" (optional) to see sample data
7. Click "Start Ingestion" to begin the transfer
8. Monitor progress and view completion report

### Flat File to ClickHouse

1. Select "Flat File" as Source and "ClickHouse" as Target
2. Select input file and configure delimiter
3. Click "Load Columns" to infer schema
4. Select columns to import
5. Enter ClickHouse connection details
6. Specify target table name
7. Click "Start Ingestion" to begin the transfer
8. Monitor progress and view completion report

### Multi-Table Join (Bonus Feature)

1. Select "ClickHouse" as Source and "Flat File" as Target
2. Connect to ClickHouse and select multiple tables
3. Configure join conditions between tables
4. Select columns to export from the joined result
5. Configure flat file settings
6. Click "Start Ingestion" to begin the transfer

## Testing

The application has been tested with the following ClickHouse example datasets:
- UK Price Paid dataset
- Ontime flights dataset

Test cases included:
1. Single ClickHouse table to flat file transfer
2. Flat file to new ClickHouse table transfer
3. Multi-table join to flat file transfer
4. Authentication failure scenarios
5. Data preview functionality

## Troubleshooting

### Common Issues

1. **Connection Errors**:
   - Verify ClickHouse host and port
   - Check if JWT token is valid and not expired
   - Confirm network connectivity

2. **File Access Issues**:
   - Ensure the application has read/write permissions
   - Verify file path is correct

3. **Data Type Mismatches**:
   - Check for compatibility between ClickHouse and flat file data types
   - Consider using type conversion options

## License

MIT License

## Acknowledgments

- ClickHouse team for their excellent database and client libraries
- Contributors and testers who helped improve this tool
