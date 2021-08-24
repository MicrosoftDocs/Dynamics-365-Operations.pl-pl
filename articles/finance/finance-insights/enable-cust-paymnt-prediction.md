---
title: Włączanie prognoz płatności odbiorcy (wersja zapoznawcza)
description: W tym temacie wyjaśniono, jak włączyć i konfigurować funkcję prognozowania płatności odbiorcy w Finance Insights.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 0b945111f360838dfa35cddb916c4fb34a41f55bdd8f3095bd97c906b7dd3dd7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768898"
---
# <a name="enable-customer-payment-predictions-preview"></a>Włączanie prognoz płatności odbiorcy (wersja zapoznawcza)

[!include [banner](../includes/banner.md)]

W tym temacie wyjaśniono, jak włączyć i konfigurować funkcję prognozowania płatności odbiorcy w Finance Insights. Włączenie funkcji w obszarze roboczym **Zarządzanie funkcją** i wprowadzenie ustawień konfiguracji na stronie **Parametry Financial Insights**. Ten temat zawiera również informacje, które mogą pomóc w skutecznym użyciu tej funkcji.

> [!NOTE]
> Przed wykonaniem poniższych kroków należy się upewnić, że wstępne kroki zostały wykonane w temacie [Konfiguracja dla modułu Finance insights](configure-for-fin-insites.md).

1. Użyj informacji ze strony środowiska w Microsoft Dynamics Lifecycle Services (LCS), aby połączyć się z podstawowym wystąpieniem usługi Azure SQL dla tego środowiska. Uruchom następujące polecenie Transact-SQL (T-SQL), aby włączyć loty dla środowiska piaskownicy. (Aby można było połączyć się zdalnie z serwerem obiektów aplikacji \[AOS\], może być konieczne włączenie dostępu do adresu IP w LCS.)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('PayPredEnableFeature', 1)`

    > [!NOTE]
    > Pomiń ten krok, jeśli używasz wersji 10.0.20 lub nowszej albo jeśli używasz stanowiska Service Fabric. Zespół Finance Insights powinien już włączyć ten lot. Jeśli nie widzisz funkcji w obszarze roboczym **Zarządzanie funkcjami** lub wystąpią problemy podczas jej włączania, wyślij wiadomość e-mail na adres <fiap@microsoft.com>. 

2. Włącz funkcję Wgląd w płatności od odbiorców:

    1. Wybierz kolejno opcje **Administrator systemu \> Obszary robocze \> Zarządzanie funkcjami**.
    2. Znajdź funkcję o nazwie **Wgląd w płatności od odbiorców (wersja zapoznawcza)**.
    3. Wybierz **Włącz teraz**.

    Funkcja wglądu do płatności odbiorcy jest teraz włączona i gotowa do skonfigurowania.

3. Skonfiguruj funkcję Wgląd w płatności od odbiorców:

    1. Wybierz kolejno opcje **Kredyty i windykacji \> Ustawienia \> Finance Insights \> Parametry Finance Insights**.

        [![Strona parametrów wglądów finansowych przed skonfigurowaniem funkcji.](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. Na stronie **Parametry Financial insights** na karcie **Wgląd w płatności od odbiorców** wybierz łącze **Wyświetl pola danych używane w modelu prognozy**, aby otworzyć stronę **Pola danych modelu prognozy**. Istnieje możliwość wyświetlenia domyślnej listy pól, które są używane do tworzenia modelu predykcyjnego sztucznej inteligencji (AI) prognoz płatności odbiorcy.

        Aby utworzyć model przewidywania za użyciu domyślnej listy pól, zamknij stronę **Pola danych dla modelu przewidywania**, a następnie na stronie **Parametry Financial Insights** ustaw wartość **Tak** opcji **Włącz funkcję**.

    3. Umożliwia określenie okresu transakcji „bardzo późno” w celu zdefiniowania, jaki jest **bardzo późny** zasobnik przewidywania w firmie.

        Dla każdej otwartej faktury system prognozuje prawdopodobieństwo płatności w trzech przedziałach: **Na czas**, **Późno** i **Bardzo późno**.

        - **Na czas** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty w terminie lub przed terminem płatności transakcji.
        - **Opóźnione** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty po terminie płatności transakcji, ale przed rozpoczęciem okresu transakcji „bardzo późno”.
        - **Bardzo opóźnione** — ten zasobnik uwzględnia płatności, które są przewidywane do zapłaty po rozpoczęciu okresu transakcji „bardzo późno”.

        > [!NOTE]
        > W przypadku zmiany okresu transakcji „bardzo późno” i wybrania opcji **Zmień próg opóźnienia** po utworzeniu modelu przewidywania plików dla odbiorców, istniejący model przewidywania jest usuwany i tworzony jest nowy model. Nowy model przewidywania przeniesie transakcje do okresu „bardzo późno” na podstawie ustawień wprowadzonych w celu jego zdefiniowania.

    4. Po zdefiniowaniu okresu transakcji „bardzo późno” wybierz opcję **Utwórz model przewidywania**, aby utworzyć model przewidywania. Sekcja **model przewidywania** na stronie **parametry Financial Insights** zawiera stan modelu przewidywania.

        > [!NOTE]
        > W dowolnym momencie podczas tworzenia modelu przewidywania można wybrać opcję **Resetuj tworzenie modelu** w celu ponownego uruchomienia tego procesu.

    Funkcja została teraz skonfigurowana i jest gotowa do użycia.

Po włączeniu i skonfigurowaniu funkcji oraz utworzeniu modelu przewidywania model przewidywania działa, sekcja **model przewidywania** na stronie **parametry Financial Insights** pokazuje dokładność modelu, tak jak to pokazano na poniższej ilustracji.

[![Dokładność modelu przewidywania na stronie parametrów Financial insights.](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Szczegóły zwolnienia

Publiczna wersja zapoznawcza Financial Insights jest dostępna dla wdrożeń próbnych w Stanach Zjednoczonych Ameryki, Europie i Zjednoczonym Królestwie. Firma Microsoft stopniowo zwiększa obsługę wielu regionów.

Funkcje publicznej wersji zapoznawczej mogą być i powinny być włączone tylko w środowiskach piaskownicy warstwy 2. Nie można migrować ustawień i modeli AI utworzonych w środowisku piaskownicy do środowiska produkcyjnego. Aby uzyskać więcej informacji, zobacz [Uzupełniające warunki użytkowania wersji zapoznawczych Microsoft Dynamics 365](../../fin-ops-core/fin-ops/get-started/public-preview-terms.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
