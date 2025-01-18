<?xml version="1.0" encoding="UTF-8"?>
<TradingBotConfig>
    <!-- API Configuration -->
    <APIConfig>
        <Platform>Deriv</Platform>
        <APIKey>YourAPIKeyHere</APIKey>
        <APISecret>YourAPISecretHere</APISecret>
        <AccountID>YourAccountIDHere</AccountID>
        <MaxAPICallsPerMinute>100</MaxAPICallsPerMinute>
    </APIConfig>

    <!-- Risk Management -->
    <RiskManagement>
        <MaxDailyLoss>10</MaxDailyLoss> <!-- Max percentage of balance to risk in a day -->
        <PositionSizing>
            <Type>Fixed</Type>
            <InitialTradeSize>10</InitialTradeSize> <!-- Initial trade size in currency -->
        </PositionSizing>
        <MaxTradesBeforeReset>5</MaxTradesBeforeReset> <!-- Max trades in Martingale sequence before reset -->
        <StopLoss>20</StopLoss> <!-- Stop after 20% loss -->
        <TakeProfit>50</TakeProfit> <!-- Take profit after 50% gain -->
    </RiskManagement>

    <!-- Martingale Strategy Settings -->
    <MartingaleStrategy>
        <StartTradeSize>10</StartTradeSize> <!-- Initial bet size (e.g., 10 USD) -->
        <Multiplier>2</Multiplier> <!-- Double the trade size after a loss -->
        <MaxLossCount>5</MaxLossCount> <!-- Max number of consecutive losses before stopping the sequence -->
        <ResetAfterWin>True</ResetAfterWin> <!-- Reset Martingale sequence after a win -->
        <MaxDrawdownPercentage>50</MaxDrawdownPercentage> <!-- Max percentage loss of the balance before stopping -->
    </MartingaleStrategy>

    <!-- Execution Settings -->
    <ExecutionSettings>
        <TradeDuration>60</TradeDuration> <!-- Binary options duration in seconds -->
        <AssetPair>EURUSD</AssetPair>
        <TradeType>CallPut</TradeType> <!-- Call or Put option for binary options -->
    </ExecutionSettings>

    <!-- Trade Conditions -->
    <TradeConditions>
        <Condition>
            <Indicator>RSI</Indicator>
            <Action>CrossBelow</Action> <!-- Sell when RSI crosses below 30 -->
            <Threshold>30</Threshold> <!-- RSI level for oversold condition -->
        </Condition>
        <Condition>
            <Indicator>RSI</Indicator>
            <Action>CrossAbove</Action> <!-- Buy when RSI crosses above 70 -->
            <Threshold>70</Threshold> <!-- RSI level for overbought condition -->
        </Condition>
    </TradeConditions>

    <!-- Logging & Analytics -->
    <Logging>
        <EnableLogging>True</EnableLogging>
        <LogLevel>INFO</LogLevel> <!-- INFO, DEBUG, ERROR, etc. -->
        <LogFilePath>/path/to/logs/martingale_bot.log</LogFilePath>
    </Logging>

    <!-- Notifications -->
    <Notifications>
        <EmailAlerts>True</EmailAlerts>
        <SMSAlerts>False</SMSAlerts>
        <TradeAlerts>
            <Success>True</Success>
            <Failure>True</Failure>
        </TradeAlerts>
    </Notifications>

    <!-- Backtesting Settings -->
    <Backtesting>
        <EnableBacktesting>True</EnableBacktesting>
        <StartDate>2024-01-01</StartDate>
        <EndDate>2024-12-31</EndDate>
        <DataFrequency>1m</DataFrequency> <!-- 1-minute candlestick data for backtesting -->
    </Backtesting>
