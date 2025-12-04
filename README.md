# Inventory Management System

Modern desktop application for inventory tracking with audit logging and Excel reporting.

## Features

- ✅ Add, update, and delete inventory items with validation
- 🔍 Real-time search with instant filtering
- 📊 Excel report generation (inventory + audit log)
- 📝 Complete audit trail with timestamps
- 🎨 Modern UI with sortable columns and context menus
- 💾 SQLite database with automatic initialization

## Requirements

- Python 3.7+
- Pillow
- openpyxl

## Installation

```bash
pip install pillow openpyxl
```

Update asset paths in code (lines with `resource_path`):
- Icon: `NE1.ico`
- Logo: `NE2.PNG`

## Quick Start

```bash
python inventory_management.py
```

The `inventory.db` database is created automatically in the parent directory.

## Usage

**Add Item**: Fill all fields → Click "Add Item"  
**Update Item**: Select item → Edit fields → Click "Update Item"  
**Delete Item**: Select item → Click "Delete Selected" → Confirm  
**Search**: Type in search box (auto-filters by name)  
**Audit Log**: Click "View Audit Log"  
**Export**: Click "Generate Report" → Choose location

**Right-click menu**: Edit, Delete, Duplicate, Copy Details

## Validation Rules

- Item Name: Max 100 chars, unique
- Quantity: Non-negative integers
- Price: Non-negative decimals
- Updated By: Max 50 chars
- All fields required

## Database Schema

**inventory**
```
id (PK), item_name (unique), quantity, price, updated_by, low_stock_threshold
```

**audit_log**
```
id (PK), action, item_id, item_name, user, timestamp
```

## Troubleshooting

- **Database errors**: Check parent directory is writable
- **Missing assets**: App runs without icon/logo files
- **Validation fails**: Ensure quantity is integer, price is decimal, names are unique

## File Structure

```
Inventory_Project/
├── inventory_management.py
├── inventory.db (auto-created)
├── NE1.ico
└── NE2.PNG
```

## License

Internal use - Nursing Experts Services

---

**Version**: 1.0 | **Status**: Production Ready
