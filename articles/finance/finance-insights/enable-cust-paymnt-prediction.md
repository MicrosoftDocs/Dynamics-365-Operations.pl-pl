---
# required metadata
title: Włączanie prognoz płatności odbiorcy
description: 'W tym temacie wyjaśniono, jak włączyć i konfigurować funkcję prognozowania płatności odbiorcy w Finance Insights.'
author: ShivamPandey-msft
ms.date: 11/03/2021
ms.topic: article
ms.prod: null
ms.technology: null
ms.search.form: null
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: '2020-05-29'
ms.dyn365.ops.version: AX 10.0.12
---

# <a name="enable-customer-payment-predictions"></a>Włączanie prognoz płatności odbiorcy

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak włączyć i konfigurować funkcję prognozowania płatności odbiorcy w Finance Insights. Włączenie funkcji w obszarze roboczym **Zarządzanie funkcją** i wprowadzenie ustawień konfiguracji na stronie **Konfiguracja Finance insights**. Ten temat zawiera również informacje, które mogą pomóc w skutecznym użyciu tej funkcji.

> [!NOTE]
> Przed wykonaniem poniższych kroków należy się upewnić, że wstępne kroki zostały wykonane w temacie [Konfiguracja dla modułu Finance insights](configure-for-fin-insites.md).

1. Włącz funkcję Wgląd w płatności od odbiorców:

    1. Otwórzz obszar roboczy **Zarządzanie funkcjami**.
    2. Wybierz **Sprawdź, czy są aktualizacje**.
    3. Na karcie **Wszystko** wyszukaj **prognozy płatności odbiorcy**. Jeśli nie znajdziesz tej funkcji, wyszukaj **(Podgląd) Prognozy płatności odbiorcy**. 
    4. Włączanie funkcji.

    Funkcja przewidywania płatności klienta jest teraz włączona i gotowa do skonfigurowania.

2. Skonfiguruj funkcję Wgląd w płatności od odbiorców:

    1. Wybierz kolejno opcje **Kredyty i windykacji \> Ustawienia \> Finance Insights \> Prognozy płatności odbiorcy**.
    2. Na stronie **Konfiguracja Financial Insights** na karcie **Prognozy płatności odbiorcy** wybierz łącze **Wyświetl pola danych używane w modelu prognozy**, aby otworzyć stronę **Pola danych modelu prognozy**. Istnieje możliwość wyświetlenia domyślnej listy pól, które są używane do tworzenia modelu predykcyjnego sztucznej inteligencji (AI) prognoz płatności odbiorcy.

        Aby utworzyć model przewidywania za użyciu domyślnej listy pól, zamknij stronę **Pola danych dla modelu przewidywania**, a następnie na stronie **Konfiguracja Finance Insights** ustaw wartość **Tak** opcji **Włącz funkcję**.

    3. Umożliwia określenie okresu transakcji „bardzo późno” w celu zdefiniowania, jaki jest **bardzo późny** zasobnik przewidywania w firmie.

        Dla każdej otwartej faktury system prognozuje prawdopodobieństwo płatności w trzech przedziałach: **Na czas**, **Późno** i **Bardzo późno**.

        - **Na czas** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty w terminie lub przed terminem płatności transakcji.
        - **Opóźnione** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty po terminie płatności transakcji, ale przed rozpoczęciem okresu transakcji „bardzo późno”.
        - **Bardzo opóźnione** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty po rozpoczęciu okresu transakcji „bardzo późno”.

        > [!NOTE]
        > W przypadku zmiany okresu transakcji „bardzo późno” i wybrania opcji **Zmień próg opóźnienia** po utworzeniu modelu przewidywania plików dla odbiorców, istniejący model przewidywania jest usuwany i tworzony jest nowy model. Nowy model przewidywania przeniesie transakcje do okresu „bardzo późno” na podstawie ustawień wprowadzonych w celu jego zdefiniowania.

    4. Po zdefiniowaniu okresu transakcji „bardzo późno” wybierz opcję **Utwórz model przewidywania**, aby utworzyć model przewidywania. Sekcja **model przewidywania** na stronie **Konfiguracja Financial Insights** zawiera stan modelu przewidywania.

        > [!NOTE]
        > W dowolnym momencie podczas tworzenia modelu przewidywania można wybrać opcję **Resetuj tworzenie modelu** w celu ponownego uruchomienia tego procesu.

    Funkcja została teraz skonfigurowana i jest gotowa do użycia.

Po włączeniu i skonfigurowaniu funkcji oraz utworzeniu modelu przewidywania model przewidywania działa, sekcja **model przewidywania** na stronie **Konfiguracja Financial Insights** pokazuje dokładność modelu.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
