# Crypto-Tech-Analyzer - Professional Technical Analysis for Cryptocurrency Trading

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Jupyter](https://img.shields.io/badge/Jupyter-Lab-F37626.svg?logo=Jupyter)](https://jupyter.org/)
[![License](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)

Профессиональный инструмент для технического анализа криптовалютных пар с интерактивными графиками и 20+ индикаторами. Данные в реальном времени с Binance API.

## 📊 Демонстрация

![Demo](https://via.placeholder.com/800x400?text=Crypto+Tech+Analyzer+Demo)

## ✨ Основные возможности

### 📈 Технические индикаторы (20+)

- **Осцилляторы**: RSI (7/14), Stochastic RSI, Williams %R, CCI
- **Трендовые**: MACD, ADX, SuperTrend
- **Скользящие средние**: SMA (20/50), EMA (12/26/50)
- **Волатильность**: Bollinger Bands, ATR (с процентом)
- **Объёмные**: OBV, Volume Ratio

### 🎯 Анализ рынка

- **Сигналы перекупленности/перепроданности**
- **Оценка силы тренда** (ADX)
- **Анализ волатильности** (ATR %)
- **Активность объёмов**
- **Определение тренда** по EMA

### 📊 Интерактивные графики

- **Candlestick chart** с индикаторами
- **Области перекупленности/перепроданности**
- **Цветовая индикация** свечей и объёмов
- **Поддержка всех таймфреймов** (1m → 1M)

## 🚀 Быстрый старт

### Установка

```bash
# Клонирование репозитория
git clone https://github.com/your-username/crypto-tech-analyzer.git
cd crypto-tech-analyzer

# Установка зависимостей
pip install -r requirements.txt

# Запуск Jupyter Lab
jupyter lab
```

### Зависимости

```
pandas          # Обработка данных
plotly          # Интерактивные графики
numpy           # Математические вычисления
requests        # API запросы к Binance
jupyterlab      # Среда выполнения
ipywidgets      # Интерактивные виджеты
```

## 📁 Структура проекта

```
crypto-tech-analyzer/
├── hummingbot_analytics.ipynb   # Основной ноутбук
├── requirements.txt              # Зависимости
├── README.md                     # Документация
└── LICENSE                       # Лицензия
```

## 🔧 Компоненты ноутбука

### 1. MarketDataProvider

```python
# Загрузка данных с Binance
data = MarketDataProvider.fetch_binance_data('BTCUSDT', '1d', 500)
ticker = MarketDataProvider.fetch_binance_ticker('BTCUSDT')
orderbook = MarketDataProvider.fetch_order_book('BTCUSDT', 20)
```

### 2. TechnicalAnalysis

```python
# Расчёт всех индикаторов
df = TechnicalAnalysis.calculate_all_indicators(df)

# Отдельные индикаторы
rsi = TechnicalAnalysis.calculate_rsi(prices, 14)
macd = TechnicalAnalysis.calculate_macd(prices)
supertrend = TechnicalAnalysis.calculate_supertrend(df)
```

### 3. Визуализация

- `show_market_overview()` - обзор рынка (цена, объём, диапазон)
- `show_technical_metrics()` - таблица индикаторов с сигналами
- `show_market_sentiment()` - графики настроений
- `show_price_chart_with_indicators()` - основной график с свечами
- `show_advanced_analysis()` - расширенный анализ (6 подграфиков)

## 📖 Использование

### Через интерфейс виджетов

1. **Выберите пару** (по умолчанию BTCUSDT)

   - Формат: `BTCUSDT`, `ETHUSDT`, `BNBUSDT`
2. **Выберите таймфрейм**

   - 1m, 3m, 5m, 15m, 30m, 1h, 2h, 4h, 6h, 8h, 12h, 1d, 3d, 1w, 1M
3. **Нажмите "Анализировать"**

### Пример вывода

#### Обзор рынка

| Метрика        | Значение | Изменение |
| --------------------- | ---------------- | ------------------ |
| Цена              | $67,845.23       | +2.45%             |
| 24ч Объем       | $25,432,567,890  | -                  |
| Диапазон 24ч | 3.2%             | -                  |

#### Технические индикаторы

| Индикатор | Значение | Сигнал       |
| ------------------ | ---------------- | ------------------ |
| RSI (14)           | 65.2             | Нейтрален |
| MACD               | Бычий       | -                  |
| ADX                | 28.5             | Сильный     |

## 🎨 Настройка графика

```python
# Кастомный layout (тёмная тема TradingView)
layout = {
    'plot_bgcolor': '#131722',
    'paper_bgcolor': '#131722',
    'font': dict(color='#d1d4dc'),
    'xaxis': dict(gridcolor='#1c2030'),
    'yaxis': dict(gridcolor='#1c2030'),
}
```

## 🔄 Поддерживаемые индикаторы

### Трендовые

- **SMA** (Simple Moving Average) - 20, 50 периодов
- **EMA** (Exponential Moving Average) - 12, 26, 50 периодов
- **MACD** (Moving Average Convergence Divergence)
- **SuperTrend** - идентификация тренда
- **ADX** (Average Directional Index) - сила тренда

### Осцилляторы

- **RSI** (Relative Strength Index) - 7, 14 периодов
- **Stochastic RSI** - стохастик от RSI
- **Williams %R** - волатильный осциллятор
- **CCI** (Commodity Channel Index)

### Волатильность

- **Bollinger Bands** - полосы ±2σ
- **ATR** (Average True Range) - с процентом

### Объёмные

- **OBV** (On-Balance Volume)
- **Volume Ratio** - отношение текущего объёма к SMA

### Уровни

- **Pivot Points** - точки разворота (R1, R2, S1, S2)
- **Fibonacci Levels** - уровни 0, 0.236, 0.382, 0.5, 0.618, 0.786, 1

## 📊 Расшифровка сигналов

| Индикатор | Перекуплен | Перепродан |
| ------------------ | -------------------- | -------------------- |
| RSI                | > 70                 | < 30                 |
| Stochastic RSI     | > 0.8                | < 0.2                |
| Williams %R        | > -20                | < -80                |
| CCI                | > +100               | < -100               |

| ADX Значение | Сила тренда |
| -------------------- | --------------------- |
| > 25                 | 💪 Сильный     |
| 20-25                | 👊 Умеренный |
| < 20                 | 🫣 Слабый       |

## 🛠️ Устранение неполадок

### Ошибка "ModuleNotFoundError: No module named 'ipywidgets'"

```bash
pip install ipywidgets
jupyter nbextension enable --py widgetsnbextension
```

### Нет данных с Binance API

- Проверьте интернет-соединение
- Убедитесь в правильности символа (например `BTCUSDT`, а не `BTC-USD`)
- Попробуйте другой таймфрейм

## 🤝 Вклад в проект

1. Форкните репозиторий
2. Создайте ветку для фичи (`git checkout -b feature/amazing-feature`)
3. Закоммитьте изменения (`git commit -m 'Add some amazing feature'`)
4. Запушьте ветку (`git push origin feature/amazing-feature`)
5. Откройте Pull Request

## 📈 Дорожная карта

- [ ] Добавить индикатор Ichimoku Cloud
- [ ] Интеграция с другими биржами (Bybit, OKX)
- [ ] Автоматическое определение уровней поддержки/сопротивления
- [ ] Экспорт отчётов в PDF
- [ ] Telegram бот для уведомлений
- [ ] Backtesting стратегий

## 📄 Лицензия

Проект распространяется под лицензией MIT. Подробнее в файле [LICENSE](LICENSE).

## 🙏 Благодарности

- [Binance API](https://binance-docs.github.io/apidocs/) за предоставление данных
- [Plotly](https://plotly.com/) за интерактивные графики
- Сообщество Hummingbot за вдохновение

---

⭐️ Не забудьте поставить звезду, если проект оказался полезным!
