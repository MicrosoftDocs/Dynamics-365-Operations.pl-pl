---
title: Konfigurowanie eksperymentu
description: W tym artykule opisano sposób konfigurowania eksperymentów w usłudze innej firmy.
author: sushma-rao
ms.date: 06/08/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 1073cdc509622279ce7388b8b406079a4e6e9e09
ms.sourcegitcommit: 427fe14824a9d937661ae21b9e9574be2bc9360b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/09/2022
ms.locfileid: "8946173"
---
# <a name="set-up-an-experiment"></a>Konfigurowanie eksperymentu

Po [zdefiniowaniu hipotezy i określeniu, jakie metryki sukcesu mają być używane](experimentation-identify.md) należy skonfigurować eksperyment w usłudze innej firmy. Na poniższym diagramie przedstawiono wszystkie kroki związane z konfigurowaniem i przeprowadzaniem eksperymentu na stronie internetowej środowiska handlu elektronicznego w systemie Dynamics 365 Commerce. Dodatkowe kroki są zawarte w odrębnych artykułach.

[ ![Proces użytkownika eksperymentu — konfiguracja.](./media/experimentation_setup.svg) ](./media/experimentation_setup.svg#lightbox)


## <a name="set-up-your-experiment-in-the-third-party-service"></a>Konfigurowanie eksperymentu w usłudze innej firmy
Teraz masz już wybraną usługę innej firmy, aby uruchomić i monitorować eksperyment, a następnie skonfigurować łącznik eksperymentów. Te wymagania wstępne wymieniono w temacie [Eksperymentowanie w systemie Dynamics 365 Commerce](experimentation-overview.md).

Wykonaj kroki wymagane do utworzenia eksperymentu w usłudze innej firmy. Jeśli łącznik jest skonfigurowany prawidłowo, pełna lista eksperymentów skonfigurowanych w ramach usługi innej firmy będzie widoczna w konstruktorze witryn Commerce w ciągu około 5 minut.

## <a name="set-up-your-success-metrics"></a>Konfigurowanie metryk sukcesu
Każdy eksperyment wymaga metryk, aby zmierzyć wpływ tych odmian i sprawdzić poprawność hipotezy. Wykonaj poniższe kroki, aby włączyć obliczanie metryk w usłudze innej firmy przy użyciu zdarzeń aktywnych telemetrii z systemu Dynamics 365 Commerce.

Aby skonfigurować wskaźniki sukcesu dla modułów gotowych, wykonaj poniższe kroki.

1. W konstruktorze witryn Commerce wybierz kartę **Strony** w lewym okienku nawigacji, a następnie wybierz stronę, na której mają być zbierane metryki. 
1. Przejdź do sekcji **Identyfikatory zdarzeń do śledzenia** w prawym okienku właściwości strony lub modułu, który chcesz śledzić.
1. Wybierz pozycję **Widok**. Zostanie wyświetlona lista wszystkich identyfikatorów zdarzeń kliknięcia. Skopiuj zdarzenie, które chcesz śledzić, a następnie wklej klucz zdarzenia w wyznaczonym miejscu w usłudze strony trzeciej. Jeśli potrzebne jest więcej niż jedno zdarzenie, należy skopiować klucze pojedynczo. 
1. W przypadku widoków stron należy użyć SHA-256 skrótu nazwy strony w konstruktorze witryn dołączonym do `.PageView`. Na przykład identyfikator zdarzenia `Homepage.PageView` to `e217eb66c7808ecc43b0f5c517c6a83b39d72b91412fbd54a485da9d8e186a9`.
1. Wykonaj wszelkie inne kroki, aby śledzić metryki zgodnie z wymaganiami usługi innej firmy.

W przypadku kliknięć w modułach niestandardowych należy wykonać poniższe kroki, aby instrumentować zdarzenia kliknięć:

1. Przygotuj obiekt **TelemetryContent** dla modułu, korzystając z poniższej funkcji. Ta funkcja przyjmuje jako dane wejściowe nazwę strony, nazwę modułu i dostarczony przez zestaw SDK domyślny obiekt telemetrii.

    ```TypeScript
    getTelemetryObject(pageName: string, moduleName: string, telemetry: ITelemetry): ITelemetryContent
    ```
    
    Poniżej przedstawiono przykład: 
    
    ```TypeScript
    private readonly telemetryContent: ITelemetryContent = getTelemetryObject(this.props.context.request.telemetryPageName!, this.props.friendlyName, this.props.telemetry);
    ```
    
1. Utwórz dane ładunku zawierające informacje o tym, co należy przechwycić. W przypadku przycisków i innych formantów statycznych można dołączyć tekst **etext**, taki jak „Shop now” lub „Search”. A w przypadku składników za pomocą kliknięcia karty produktu można wysłać **identyfikator rekordu** produktu lub identyfikatora produktu.

    ```TypeScript
    getPayloadObject(eventType: string, telemetryContent: ITelemetryContent, etext: string, recid?: string): IPayLoad
    ```
    Jako przykład formantów statycznych należy przekazać ciąg tekstowy przycisku, tak jak pokazano poniżej:

    ```TypeScript
    const payLoad = getPayloadObject('click', this.props.telemetryContent, 'Shop Now', '');
    ```
    Jako przykład klikania produktu, przekaż rekord produktu recordId, tak jak pokazano poniżej:

    ```TypeScript
    const payLoad = getPayloadObject('click', telemetryContent!, '', product.RecordId.toString());
    ```
    
1. Wywołaj funkcję **OnClick**, aby zarejestrować zdarzenie.

    ```TypeScript
    onTelemetryClick = (telemetryContent: ITelemetryContent, payLoad: IPayLoad, linkText: string) => () =>
    ```

    Poniżej przedstawiono przykład:

    ```TypeScript
    onClick: onTelemetryClick(this.props.telemetryContent, payLoad, linkText)
    ```

## <a name="previous-step"></a>Poprzedni krok
[Określanie hipotezy i ustalanie metryki eksperymentu](experimentation-identify.md) 


## <a name="next-step"></a>Następne kroki
[Łączenie i edytowanie eksperymentu](experimentation-connect-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
