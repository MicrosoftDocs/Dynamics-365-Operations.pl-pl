---
title: Raport warunków płatności w transakcjach handlowych (PL-00053)
description: Ten artykuł zawiera informacje dotyczące raportu Warunki płatności oraz informacje dotyczące jego konfigurowania i generowania.
author: sndray
ms.date: 05/06/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Poland
ms.author: sndray
ms.search.validFrom: ''
ms.dyn365.ops.version: 10.0.24
ms.openlocfilehash: e0bf422735962d8464b7aa236f8433a56d3ae85f
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8887836"
---
# <a name="payment-terms-in-commercial-transactions-report"></a>Raport warunków płatności w transakcjach handlowych

[!include [banner](../includes/banner.md)]

W tym artykule opisano sposób skonfigurowania i wygenerowania raportu Warunki płatności wymaganego dla firm w Polsce. Do 31 stycznia każdego roku niektóre firmy muszą przesłać raport o warunkach płatności w transakcjach handlowych za ubiegły rok. Firmy przesyłają raport za pośrednictwem zgłoszenia urzędu skarbowego, wprowadzając dane, o które wnioskuje kreator. System wygeneruje raport.

Raportu można użyć do wygenerowania sumego raportu i szczegółowego raportu w celu ułatwienia ręcznego wprowadzania informacji do aplikacji urzędu skarbowego. Obecnie nie ma opcji automatycznej integracji z witryną urzędu skarbowego.

Raport warunków płatności jest generowany za pomocą narzędzia Raportowanie elektroniczne. Wygenerowany raport ma format Microsoft Excel i zawiera następujące pliki:

- **Szczegółowy raport AP** — lista płatności otrzymanych w ciągu 30 dni w okresie od 31 do 60 dni, w okresie od 61 do 120 dni oraz po 120 dniach
- **Szczegółowy raport AR** — lista płatności zrobionych w ciągu 30 dni w okresie od 31 do 60 dni, w okresie od 61 do 120 dni oraz po 120 dniach
- **Raport zbiorczy** – Konsolidacja szczegółowych raportów dotyczących świadczeń a także płatności, które nie zostały odebrane i wykonane w okresie raportu.

## <a name="prerequisites"></a>Wymagania wstępne

W programie Finance zaimportuj następujące konfiguracje raportowania elektronicznego (ER) z repozytorium globalnego.

| Nazwa konfiguracji ER              | Typ konfiguracji |
|------------------------------------|--------------------|
| Statystyki na fakturach             | Model              |
| Mapowanie modelu warunków płatności        | Mapowanie modelu      |
| Raport warunków płatności (PL)          | Format (eksportowanie) |

Aby uzyskać więcej informacji na temat pobierania konfiguracji modułu ER, zapoznaj się z tematem [Pobieranie konfiguracji ER z repozytorium globalnego](../../fin-ops-core/dev-itpro/analytics/er-download-configurations-global-repo.md).

Zaimportuj najnowsze wersje konfiguracji. Opis wersji zazwyczaj zawiera numer artykułu z bazy wiedzy Microsoft Knowledge Base (KB), który wyjaśnia zmiany wprowadzone w wersji konfiguracji systemu. Użyj **funkcji wyszukiwania** problemów w portalu [usługi LCS](https://lcs.dynamics.com/v2), aby znaleźć informacje o zmianach według numeru artykułu z Bazy wiedzy.

> [!NOTE]
> Po zaimportowaniu wszystkich konfiguracji raportowania elektronicznego z powyższej tabeli ustaw **Ustawione domyślne mapowanie modelu** na **Tak** w przypadku konfiguracji **Mapowanie modelu warunków płatności**.

### <a name="enable-features-in-feature-management"></a>Włącz nowe funkcje w zarządzaniu funkcjami

Zalecamy włączenie funkcji poprawiających wydajność raportu **Warunki płatności w transakcjach handlowych**.

1. Przejdź do obszaru **Zarządzanie funkcjami** > **Wszystkie**.
2. Na liście funkcji znajdź i wybierz następujące funkcje:

    - **Optymalizacja czasu tworzenia źródła danych zapytania podczas wykonywania raportów raportowania elektronicznego**
    - **Optymalizuj zużycie pamięci zestawów danych w środowisku uruchomieniowym raportów raportowania elektronicznego**

3. Wybierz **Włącz teraz**.

## <a name="scenarios-covered"></a>Objęte scenariusze

Generowanie raportów obejmuje następujące scenariusze:

- Transakcje odbiorcy i dostawcy filtrowane według grupy księgowania i dostawcy lub grupy klientów:

    - Płatności
    - Transakcje otwarte

- Dni płatności, które są obliczane w następujący sposób:

    - Według daty płatności lub rozliczenia
    - Według daty dokumentu lub faktury
    - Według rat zgodnie z harmonogramem płatności

- Kwoty w walucie rozliczeniowej
- Korekty kursowe lub przesądy uwzględnione jako część kwoty płatności
- Faktury projektu
- Noty korygujące
- Wynagrodzenie między rachunkami dostawcy i klienta
- Faktury zaliczkowe lub przedpłaty

> [!NOTE]
> Raport nie zawiera całkowicie rozliczonych not korygujące.

### <a name="payment-terms-in-commercial-transactions-report-and-one-voucher"></a>Warunki płatności w raporcie transakcji handlowych i Jeden voucher

Użycie funkcji Jeden załącznik wprowadza ograniczenie dalszych warunków płatności w raportach transakcji handlowych dla danych, jeśli został zastosowany jeden załącznik. Jeśli księgujesz transakcje, które są częścią raportu Warunki płatności w transakcjach handlowych, zalecamy ustawienie parametru **Zezwalaj na wiele transakcji w ramach jednego vouchera** na stronie **Parametry księgi głównej** na **Nie** w Twojej osobie prawnej. Aby uzyskać informacje o funkcji Jednego załącznika, zobacz [Jeden załącznik](../general-ledger/one-voucher.md).

## <a name="run-the-statistics-on-invoices-process"></a>Uruchamianie procesu Statystyki faktur

Przed wygenerowanie raportu Warunki płatności uruchom proces **Statystyki faktur** z modułów **Rozrachunki z dostawcami** i **Rozrachunki z odbiorcami**, aby wygenerować określony widok historii płatności. Ten proces jest używany w raporcie Warunki płatności w celu uzyskania wszystkich faktur, które zostały całkowicie lub częściowo zapłacone. Możesz uruchomić ten proces w czasie rzeczywistym lub zaplanować jego działanie w tle poprzez przetwarzanie wsadowe.

1. Przejdź do: **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Statystyki dotyczące faktur** lub **Rozrachunki z odbiorcami** \> **Zadania okresowe** \> **Statystyki faktur**.
2. Wybierz pozycję **Oblicz statystyki**.
3. Wybierz daty „od” i „do”.
4. Wybierz profil księgowania dostawcy lub odbiorcy. Profile księgowania umożliwiają łatwe uwzględnianie w generowanym raporcie transakcji dostawcy lub odbiorcy dla wszystkich dostawców lub odbiorców, grupy dostawców lub odbiorców albo jednego dostawcy lub odbiorcy. Aby wybrać wszystkich dostępnych dostawców i odbiorców, należy pozostawić to pole puste.
5. Opcjonalnie można wybrać dostawcę lub grupę klientów, aby zastosować dodatkowy filtr transakcji. Aby wybrać wszystkich dostępnych dostawców i odbiorców, należy pozostawić to pole puste.
6. Wybierz przycisk **OK**, aby uruchomić proces.

## <a name="generate-a-payment-terms-report"></a>Wygeneruj raport o warunkach płatności

1. Przejdź do: **Rozrachunki z dostawcami** \> **Zadania okresowe** \> **Statystyki dotyczące faktur** lub **Rozrachunki z odbiorcami** \> **Zadania okresowe** \> **Statystyki faktur**.
2. Wybierz **raport Warunki płatności**, a następnie wybierz powiązany format raportu ER.
3. W polu **Szczegóły** wybierz typ szczegółów raportu. Możesz wybrać wiele opcji.

    - Szczegóły AP
    - Szczegóły AR
    - Wznów

4. Wybierz język raportu. Bieżący raport jest tłumaczony na angielski (**en-us**) i na polski (**pl**).
5. Wybierz daty „od” i „do”.
6. Wybierz dostawcę lub grupę klientów, aby odfiltrować określone transakcje.
7. Wybierz profil odbiorcy lub dostawcy, aby filtrować określone transakcje.
8. Kliknij przycisk **OK**, aby wygenerować raport.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
