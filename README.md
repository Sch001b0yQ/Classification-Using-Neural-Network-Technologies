# README – Розробка програми для аналізу та класифікації образів із використанням нейромережевих технологій ⸺ дипломна робота
## 1. Основні бібліотеки
### Встановіть Python ≥ 3.10 (з офіційного python.org) і переконайтесь, що під час інсталяції ввімкнено опцію Add Python to PATH.
- PyTorch ≥ 2.2
- torchvision
- timm
- opencv‑python‑headless
- pandas, numpy
- scikit‑learn
- matplotlib, seaborn
- tqd
- ipywidgets
## 2. Датасети
1. [Датасет GroceryStoreDataset](https://github.com/marcusklasson/GroceryStoreDataset)
2. Власний датасет було завантажено у репозиторій із кодом
## 3. Установіть Jupyter Notebook
## 4. Запуск ноутбука
- У браузері відкрийте ноутбук і виконуйте комірки зверху вниз
- Перша комірка встановить усі залежності
- Для коректної роботи потрібно вказати правильний шлях до датасету ( Приклад: DATA_DIR = r"D:\datasets\GroceryStore\dataset" )
## 5. Поширені проблеми
- CUDA out of memory - Зменшіть BATCH_SIZE; вимкніть AMP
- Клітинка «зависла» (progress‑bar не рухається) - Спробуйте num_workers = 0; вимкніть persistent_workers; перевірте швидкість диска; перезапустіть ядро (Kernel → Restart)
- Jupyter kernel died / Kernel Restarting - часто вказує на нестачу GPU/CPU‑RAM або конфліктну версію CUDA; зменшіть BATCH_SIZE чи модель; оновіть драйвер NVIDIA та PyTorch
- ModuleNotFoundError - Виконайте першу клітинку з pip install …; після інсталяції перезапустіть ядро
- RuntimeError: size mismatch - NUM_CLASSES не відповідає кількості класів у датасеті; змініть змінну та перезапустіть блок побудови моделі
- torch.cuda.is_available() → False - Встановіть PyTorch із підтримкою CUDA (pip install torch==2.2.1+cu118); перевірте nvcc --version
- Dataloader зависає у Windows після 1‑го батчу - У ноутбуці встановіть num_workers = 0; у скриптах додайте if __name__ == '__main__':
