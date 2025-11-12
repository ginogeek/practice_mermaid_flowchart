```mermaid
flowchart TD
    A["開始"] --> B{"現地手配日時 = 空欄 ?"}
    B -- Yes --> C["NULL"]
    B -- No --> D{"カードID = 空欄 ?"}
    
    D -- Yes --> E["NULL"]
    D -- No --> F{"時刻 >= 17時 ?"}
    
    F -- Yes --> G["false"]
    F -- No --> H["true"]
    
    H --> I["WORKDAY(日付-1, 休日リスト)"]
    
    G --> J{"曜日 > 1 ?"}
    J -- Yes --> K["WORKDAY(日付, 休日リスト)"]
    J -- No --> L{"曜日 = 1 ?"}
    
    L -- Yes --> M["WORKDAY(日付-1, 休日リスト)"]
    L -- No --> N["NULL"]
