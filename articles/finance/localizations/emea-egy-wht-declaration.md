---
title: Deklaracja potrąconej zaliczki na podatek dla Egiptu
description: W tym temacie wyjaśniono, jak skonfigurować i wygenerować deklaracje podatku u źródła dla Egiptu.
author: sndray
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, Developer, IT Pro
ms.reviewer: kfend
ms.search.scope: ''
ms.search.region: Global
ms.author: tfehr
ms.search.validFrom: 2017-06-20
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: e0d13a2de9acaa8b1c896e130b4dabb222e45dcb
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881429"
---
#  <a name="withholding-tax-declaration-for-egypt-eg-00005"></a>Deklaracja potrąconej zaliczki na podatek dla Egiptu (EG-00005)

[!include[banner](../includes/banner.md)]

[!include[banner](../includes/preview-banner.md)]

## <a name="overview"></a>Omówienie
W tym temacie wyjaśniono, jak skonfigurować i wygenerować deklarację podatku u źródła oraz formularze 41 i 11 deklaracji podatku u źródła dla osób prawnych w Egipcie 

Wszystkie jednostki Te muszą przygotować formularz 41, który podsumowuje wszystkie podatki zatrzymane od lokalnych dostawców i usługodawców. Oprócz formularza 41 należy wygenerować formularz 11, aby wyszczególnić wszystkie zatrzymane podatki od dostawców zagranicznych. 

Raport **Deklaracji potrąconej zaliczki na podatek** w Dynamics 365 Finance zawiera następujące raporty:

- Formularz deklaracji Nie. 41
- Formularz deklaracji Nie. 11
    
    
## <a name="prerequisites"></a>Wymagania wstępne
Podstawowy adres firmy musi być w Egipcie.
W obszarze roboczym **Zarządzanie funkcjami** włącz następujące funkcje:

   - **Globalna potrącona zaliczka na podatek**

Aby uzyskać więcej informacji o włączaniu funkcji, zobacz [Zarządzanie funkcjami — omówienie.](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md)

1. Przejdź do **Podatek** > **Konfiguracja** > **Parametry** > **Parametry księgi głównej**, a następnie na karcie **Potrącona zaliczka** na podatek ustaw opcję **Włącz globalną potrącanie zaliczki na podatek** na wartość **Tak**.
2. W obszarze roboczym **Raportowanie elektroniczne** zaimportuj następujące formaty raportowania elektronicznego z repozytorium:

    - Deklaracja WHT Excel (EG)

    > [!NOTE]
    > Powyższy format jest oparty na **Modelu deklaracji podatkowej** i korzysta z **Mapowania modelu deklaracji podatkowej**. Ta dodatkowa konfiguracja jest automatycznie importowana.

Aby uzyskać więcej informacji dotyczących importowania konfiguracji raportowania elektronicznego, zobacz temat [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

## <a name="download-electronic-reporting-configurations"></a>Pobieranie konfiguracji raportowania elektronicznego

Wdrażanie formularzy deklaracji WHT dla Egiptu opiera się na konfiguracjach elektronicznego raportowania (ER). Aby uzyskać więcej informacji o możliwościach i pojęciach dotyczących raportowania konfigurowalnego, zobacz temat [Raportowanie elektroniczne](../../fin-ops-core/dev-itpro/analytics/general-electronic-reporting.md).

W przypadku środowisk produkcyjnych i testów akceptacyjnych użytkownika (UAT) postępuj zgodnie z instrukcjami w temacie [Pobieranie konfiguracji raportowania elektronicznego z usługi Lifecycle Services](../../fin-ops-core/dev-itpro/analytics/download-electronic-reporting-configuration-lcs.md).

Aby wygenerować deklaracje potrącenia podatku w egipskiej osobie prawnej, musisz przesłać następujące konfiguracje:

- Wersja pliku model.version.82.xml lub jego nowsza wersja
- Wersja pliku mapping.version.82.133.xml lub jego nowsza wersja
- Deklaracja WHT Excel (EG).version.82.21 lub nowsza wersja

Po pobraniu konfiguracji ER z usługi Lifecycle Services (LCS) lub repozytorium globalnego wykonaj następujące kroki.

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz kafelek **Konfiguracje raportowania**.
1. Na stronie **Konfiguracje**, w okienku akcji wybierz **Import/eksport > Załaduj z pliku XML**.
1. Przekaż wszystkie pliki w kolejności, w jakiej są one wymienione w poprzednich plikach. Po przekazaniu wszystkich konfiguracji drzewo konfiguracji powinno być obecne w Finance.

## <a name="set-up-application-specific-parameters"></a>Konfigurowanie parametrów specyficznych dla aplikacji

Opcja parametrów specyficznych dla aplikacji umożliwia użytkownikom określenie kryteriów klasyfikacji i obliczania transakcji podatkowych w każdym wierszu generowanego raportu, w zależności od konfiguracji **grupy pozycji potrąconej zaliczki na podatek** lub innych kryteriów określonych w definicji wyszukiwania.

Formularz 41 deklaracji potrąconej zaliczki na podatek zawiera określoną kolumnę, w której transakcja potrąconej zaliczki na podatek musi zostać sklasyfikowana zgodnie z klasyfikacją urzędu skarbowego o nazwie **Typ kodu rabatu**. Zamiast ująć te nowe klasyfikacje jako nowe dane wprowadzania podczas księgowania transakcji, klasyfikacje będą ustalane na podstawie różnych wyszukiwania wprowadzonych w **Konfiguracje** > **Konfigurowanie parametrów specyficznych dla aplikacji** > **Konfiguracja**, aby spełnić wymagania zgłaszania zaliczki w Egipcie. 

Następująca konfiguracja służy do klasyfikowania transakcji w raporcie Deklaracja potrąconej zaliczki na podatek 41:

- **DiscountTaxTypeLookup** -> Kolumna nr 18 

Wykonaj następujące kroki, aby skonfigurować różne wyszukiwania używane do generowania deklaracji WHT i powiązanych raportów księgowych. 

1. W obszarze roboczym **Raportowanie elektroniczne** wybierz **Konfiguracje** > **Konfiguracja**, aby skonfigurować zasady określania, w jaki sposób transakcje są klasyfikowane w raporcie deklaracji WHT. 
2. Wybierz bieżącą wersję, a na skróconej karcie **Wyszukiwania** wybierz nazwę wyszukiwania. Na przykład **DiscountTaxTypeLookup**. To wyszukiwania identyfikują listę typów rabatów wymaganych przez urząd skarbowy.
3. Na skróconej karcie **Warunki** wybierz pozycję **Dodaj**, a w nowym wierszu w kolumnie **Wynik wyszukiwania** zaznacz powiązany wiersz reprezentujący klasyfikację w **Kolumnie 18**.
4. W kolumnie **Grupa pozycji podatku u źródła** wybierz powiązany kod, który jest używany do identyfikacji klasyfikacji. Na przykład **Dozwolony rabat**.  
5. Powtórz kroki 3 i 4 dla wszystkich dostępnych wyszukiwania.
6. Wybierz znowu opcję **Dodaj**, aby uwzględnić ostateczny wiersz rekordu, a następnie w kolumnie **Wynik wyszukiwania** wybierz opcję **Nie dotyczy**. 
7. W kolumnach pozostałych wybierz opcję **Niepuste**. 

> [!NOTE]

## <a name="set-up-general-ledger-parameters"></a>Konfigurowanie parametrów księgi głównej

Aby wygenerować raporty formularza deklaracji WHT w formacie Microsoft Excel, zdefiniuj format raportu elektronicznego na stronie **Parametry księgi głównej**.

1. Wybierz kolejno opcje **Podatek** > **Ustawienia** > **Parametry księgi głównej**.
2. Na karcie **Potrącona zaliczka** na podatek w polu **Mapowanie formatu deklaracji WHT** wybierz pozycję **Deklaracja WHT Excel (EG)**. Jeśli pole to jest puste, standardowy raport podatku zostanie wygenerowany w formacie SSRS.


![Formularz deklaracji](media/egypt-wht-declaration-setup1.png)

## <a name="generate-the-withholding-declaration-forms"></a>Generowanie formularzy deklaracji potrąconej zaliczki na podatek
Proces przygotowywania i przesyłania formularza deklaracji potrąconej zaliczki na podatek dla określonego okresu jest oparty na transakcjach potrącenia zaliczki na podatek zaksięgowanych podczas zadania rozliczania i księgowania podatku od płatności. Aby uzyskać więcej informacji na temat globalnej potrąconej zaliczki na podatek, zobacz [Globalna potrącona zaliczka na podatek](../general-ledger/global-withholding-tax-overview.md).

Aby wygenerować raport deklaracji podatkowej, należy wykonać następujące kroki.

1. Przejdź do **Podatek** > **Deklaracje** > **Zaliczka na podatek** > **Płatność zaliczki na podatek*.
2. Wybierz okres rozliczeniowy, a następnie datę rozpoczęcia dla raportu. 
3. Wprowadź datę transakcji, a następnie wybierz opcję **OK**.
4. W otwieraowym oknie dialogowym wybierz jeden lub więcej typów formularzy **Formularz nr 41 **, **Formularz nr 11** lub **Brak**. W przypadku wybrania opcji **Brak** zostanie wygenerowany raport standardowy. 
5. Wybierz język. Wszystkie raporty są tłumaczone w języku **en-us** i **ar-eg**.
6. Wprowadź oddział i nazwę banku, w którym zostanie zapłacony podatek.
7. Wybierz typ biznesowy, a następnie wprowadź czek i numery dokumentów. 
8. Wprowadź typ jednostki. 
9. Wprowadź nazwisko zarejestrowanej osoby w celu przypisania formularza i wybierz **OK**, aby potwierdzić generowanie raportu. 

 
[!INCLUDE[footer-include](../../includes/footer-banner.md)]
