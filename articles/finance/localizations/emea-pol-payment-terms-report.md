---
title: Raport warunków płatności w transakcjach handlowych (PL-00053)
description: Ten temat zawiera informacje dotyczące raportu Warunki płatności oraz informacje dotyczące jego konfigurowania i generowania.
author: sndray
ms.date: 01/07/2022
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
ms.openlocfilehash: 185cda99ab03189b25e4d79d080e62ffedd483d5
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/12/2022
ms.locfileid: "7965127"
---
# <a name="payment-terms-in-commercial-transactions-report"></a>Raport warunków płatności w transakcjach handlowych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób skonfigurowania i wygenerowania raportu Warunki płatności wymaganego dla firm w Polsce. Do 31 stycznia każdego roku niektóre firmy muszą przesłać raport o warunkach płatności w transakcjach handlowych za ubiegły rok. Firmy przesyłają raport za pośrednictwem zgłoszenia urzędu skarbowego, wprowadzając dane, o które wnioskuje kreator. System wygeneruje raport.

Raportu można użyć do wygenerowania sumego raportu i szczegółowego raportu w celu ułatwienia ręcznego wprowadzania informacji do aplikacji urzędu skarbowego. Obecnie nie ma opcji automatycznej integracji z witryną urzędu skarbowego.

Raport warunków płatności jest generowany za pomocą narzędzia Raportowanie elektroniczne. Wygenerowany raport ma format Microsoft Excel i zawiera następujące pliki:

- **Szczegółowy raport AP** — lista płatności otrzymanych w ciągu 30 dni w okresie od 31 do 60 dni, w okresie od 61 do 120 dni oraz po 120 dniach
- **Szczegółowy raport AR** — lista płatności zrobionych w ciągu 30 dni w okresie od 31 do 60 dni, w okresie od 61 do 120 dni oraz po 120 dniach
- **Raport zbiorczy** – Konsolidacja szczegółowych raportów dotyczących świadczeń a także płatności, które nie zostały odebrane i wykonane w okresie raportu.

## <a name="prerequisites"></a>Wymagania wstępne

Zanim raport zostanie wygenerowany po raz pierwszy, pobierz następujące modele i formaty z usługi Microsoft Dynamics Lifecycle Services (LCS):
    
- Statystyki faktur (model) wersja 41
- Mapowanie modelu warunków płatności w wersji 41.1
- Raport warunków płatności (PL) w wersji 41.1

> [!NOTE]
> Aby uzyskać więcej informacji dotyczących importowania konfiguracji ER, zobacz temat [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

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
