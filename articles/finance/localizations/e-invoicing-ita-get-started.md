---
title: Rozpoczynanie pracy z fakturowaniem elektronicznym dla Włoch
description: Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Włoch.
author: gionoder
ms.date: 09/22/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "97423"
- intro-internal
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-07-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 8bbb78f0b20ec12fe59dfb3c656b3177b2464004
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356084"
---
# <a name="get-started-with-electronic-invoicing-for-italy"></a>Rozpoczynanie pracy z fakturowaniem elektronicznym dla Włoch

[!include [banner](../includes/banner.md)]


> [!IMPORTANT]
> Faktury elektroniczne dla Włoch może obecnie nie obsługiwać wszystkich funkcji dostępnych dla faktur elektronicznych w Microsoft Dynamics 365 Finance i Dynamics 365 Supply Chain Management. 

Ten temat zawiera informacje, które pomogą w rozpoczęciu pracy z Faktury elektroniczne dla Włoch. Przeprowadza użytkownika przez kolejne etapy konfiguracji, które są zależne od kraju w usługach Regulatory Configuration Services (RCS) i Finance. Prowadzi również użytkownika przez proces przesyłania faktur elektronicznych, które są generowane za pośrednictwem usługi w formacie **FatturaPA** specyficznym dla Włoch, oraz wyjaśnia, jak przeglądać wyniki przetwarzania.

## <a name="prerequisites"></a>Wymagania wstępne

Przed wykonaniem kroków opisanych w tym temacie należy wykonać kroki opisane w temacie [Rozpoczynanie pracy z Fakturami elektronicznymi](e-invoicing-get-started.md).

## <a name="rcs-setup"></a>Konfiguracja RCS

Podczas instalacji RCS należy wykonać następujące zadania:

1. Zaimportuj funkcję fakturowania elektronicznego do eksportu faktur elektronicznych odbiorcy w formacie **FatturaPA**.
2. Przejrzyj konfiguracje formatów wymagane do generowania, przesyłania i odbierania odpowiedzi na faktury elektroniczne.
3. Skonfiguruj zdarzenia obsługujące scenariusze przesyłania faktur elektronicznych.
4. Opublikuj funkcję fakturowania elektronicznego.

> [!NOTE]
> „Funkcja fakturowania elektronicznego” to ogólna nazwa zasobu, który jest skonfigurowany i opublikowany w celu wykorzystania serwera Faktur elektronicznych. W takim przypadku eksport elektronicznych faktur klienta jest funkcją fakturowania elektronicznego, którą skonfigurujesz.

## <a name="import-the-e-invoicing-feature"></a>Importuj funkcję fakturowania elektronicznego

1. Zaloguj się do swojego konta RCS.
2. Otwórz nowy obszar roboczy **Funkcje globalizacji**, a następnie w obszarze **Funkcje** wybierz kafelek **Fakturowanie elektroniczne**.
3. Na stronie **Funkcje fakturowania elektronicznego** wybierz opcję **Importuj** w celu zaimportowania funkcji fakturowania elektronicznego z repozytorium globalnego.

    > [!NOTE]
    > Jeśli lista dostępnych funkcji jest niewidoczna, wybierz opcję **Synchronizuj**. 

4. Wybierz funkcję **Eksport faktur elektronicznych (IT)**, a następnie wybierz opcję **Importuj**.

![Importowanie funkcji eksportu faktur elektronicznych (IT).](media/e-Invoicing-services-get-started-ITA-Select-Import-e-Invoicing-feature.png)

Po zaimportowaniu funkcji **Eksportowanie faktur elektronicznych (IT)** z repozytorium globalnego zostaną również zaimportowane wszystkie ustawienia opisane w następnych sekcjach.

## <a name="create-a-new-version-of-the-e-invoices-export-it-feature"></a>Utwórz nową wersję funkcji Eksportowania faktur elektronicznych (IT)

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz **Nowa**. 

    ![Dodawanie nowej wersji funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-ITA-Select-New-e-Invoicing-feature-version.png)

    Następnie skonfigurujesz formaty raportowania elektronicznego (ER), które są skojarzone z funkcją fakturowania elektronicznego.

2. Na karcie **Konfiguracje** wybierz opcję **Dodaj**, aby zarządzać wersjami konfiguracji.

    ![Zarządzanie wersjami konfiguracji funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-configurations.png)

    W tym kroku są dodawane i konfigurowane formaty ER różnych plików używanych do eksportowania włoskich faktur elektronicznych. W przypadku włoskich faktur elektronicznych FatturaPA należy stosować następujące standardowe konfiguracje lub odpowiednie niestandardowe konfiguracje używane do fakturowania elektronicznego:

    - Faktura sprzedaży (IT)
    - Faktura projektu (IT)

    Podczas tworzenia funkcji fakturowania elektronicznego pochodzącej z innej funkcji fakturowania elektronicznego, wszystkie formaty ER są dziedziczone z oryginalnej funkcji.

3. Wybierz określoną konfigurację pliku formatu ER.
4. Wybierz opcję **Edytuj** lub **Wyświetl**, aby otworzyć stronę **Projektant formatów**.

    ![Otwieranie strony Projektanta formatów.](media/e-Invoicing-services-get-started-ITA-Configuration-ER-format-designer.png)

5. Strona **Projektant formatów** umożliwia edytowanie i wyświetlanie konfiguracji plików formatu ER.

    ![Strona projektanta formatu.](media/e-Invoicing-services-get-started-ITA-ER-format-designer.png)

## <a name="manage-the-e-invoicing-feature-setups"></a>Zarządzaj konfiguracjami funkcji fakturowania elektronicznego

- Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** wybierz opcję **Dodaj**, **Usuń** lub **Edytuj**, aby zarządzać konfiguracjami funkcji fakturowania w systemie.

![Zarządzanie konfiguracjami funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-ITA-Manage-e-Invoicing-feature-setup.png)

W tym kroku można skonfigurować zdarzenia dotyczące faktur elektronicznych, łącznie z generowaniem plików wyjściowych XML w formacie **FatturaPA** i cyfrowym (jeśli jest to wymagane).

### <a name="configure-the-sales-invoice-feature-setup"></a>Konfigurowanie ustawień funkcji faktur sprzedaży

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Ustawienia** w kolumnie **Ustawienia funkcji** wybierz opcję **Faktura sprzedaży**.
2. Wybierz opcję **Edycja**.
3. Na stronie **Ustawienia wersji funkcji** wybierz kartę **Akcje**, aby zarządzać listą akcji. Akcje definiują listę operacji, które muszą być uruchomione w kolejności sekwencyjnej, aby wykonać pełne wykonanie zdarzenia.

    ![Karta Akcje.](media/e-Invoicing-services-get-started-ITA-Select-Actions.png)

    | Identyfikator akcji | Nazwa akcji        | Opis akcji                                     |
    |-----------|--------------------|--------------------------------------------------------|
    | 1         | Przekształć dokument | Utwórz plik XML faktury elektronicznej w formacie **FatturaPA**. |
    | 2         | Podpisz dokument      | Zastosuj podpis cyfrowy do pliku XML.             |

4. Wybierz kartę **Reguły stosowania**, aby wyświetlić i zachować reguły stosowania. Reguły stosowania definiują kontekst, w którym akcja będzie uruchamiana.

    ![Karta Reguły zastosowania.](media/e-Invoicing-services-get-started-ITA-Select-Applicability-rules.png)

5. Wybierz kartę **Zmienne**, aby wyświetlić i zachować zmienne.

    ![Karta Zmienne.](media/e-Invoicing-services-get-started-ITA-Select-Variables.png)

6. Umożliwia zdefiniowanie zmiennych publicznych wymaganych do uruchomienia akcji.

### <a name="configure-the-project-invoice-feature-setup"></a>Konfigurowanie ustawień funkcji faktur projektu 

Kroki i ustawienia wymagane do skonfigurowania funkcji **Faktura projektu** są bardzo podobne do kroków i ustawień konfiguracji funkcji **Faktura sprzedaży**. Podczas pracy z fakturami projektu należy zapoznać się z procedurami faktur sprzedaży.

## <a name="assign-the-e-invoicing-feature-to-the-environment"></a>Przypisz funkcję fakturowania elektronicznego do środowiska

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Środowisko** wybierz **Włącz**.
2. W polu **Środowiska** wybierz środowisko.
3. W polu **Obowiązuje od** wybierz datę, kiedy nowe środowisko powinno zostać wprowadzone.
4. Wybierz **Włącz**. 

![Włączanie środowiska fakturowania elektronicznego.](media/e-Invoicing-services-get-started-ITA-Enable-e-Invoicing-environment.png)

## <a name="publish-the-e-invoicing-feature"></a>Opublikuj funkcję fakturowania elektronicznego

Funkcję fakturowania elektronicznego można opublikować, zmieniając stan wersji na **Ukończono** lub **Opublikowano**.

### <a name="change-the-version-status-to-completed"></a>Zmień stan wersji na Ukończone

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Wersja robocza**.
2. Wybierz **Zmień status \> Zakończone**. 

### <a name="change-the-version-status-to-published"></a>Zmień stan wersji na Opublikowane 

1. Na stronie **Funkcje fakturowania elektronicznego** na karcie **Wersje** wybierz wersję funkcji fakturowania elektronicznego, która ma stan **Ukończono**.
2. Wybierz **Zmień status \> Opublikuj**.

![Zmiana stanu funkcji fakturowania elektronicznego.](media/e-Invoicing-services-get-started-ITA-Change-status-of-e-Invoicing-feature.png)

## <a name="set-up-electronic-invoicing-integration-in-finance"></a>Skonfiguruj integrację Faktury elektroniczne w Finance

Podczas instalacji Finance należy wykonać następujące zadania:

1. Importuj model danych modelu ER, mapowanie modelu danych ER i konfiguracje kontekstowe dla faktur elektronicznych FatturaPA.
2. Skonfiguruj certyfikat, który jest wymagany do cyfrowego podpisywania włoskich faktur elektronicznych.

### <a name="import-the-er-data-model-data-model-mapping-and-formats"></a>Importowanie modelu danych ER, mapowania modelu danych i formatów

1. W obszarze roboczym **Raportowanie elektroniczne** sprawdź, czy dostawca konfiguracji **Usługi dokumentów biznesowych** jest skonfigurowany jako **Aktywny**.
2. Wybierz **Repozytoria**.
3. Wybierz pozycję **Zasób globalny \> Otwórz**.
4. Importowanie **Modelu faktury**, **Mapowania modelu faktury** i **Modelu kontekstu faktury dla odbiorcy**.

#### <a name="turn-on-the-feature-for-exporting-customer-electronic-invoices-for-italy"></a>Włącz funkcję, aby wyeksportować faktury elektroniczne dla odbiorcy we Włoszech

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Funkcje** zaznacz pole wyboru **Włączone** w wierszu dla odwołania do funkcji **IT00036**.

![Włączanie funkcji FatturaPA.](media/e-Invoicing-services-get-started-ITA-Enable-FatturaPA-feature.png)

#### <a name="configure-electronic-documents"></a>Konfiguracja dokumentów elektronicznych

1. Przejdź do **Administrowanie organizacją \> Konfiguracja \> Parametry dokumentu elektronicznego**.
2. Na karcie **Dokument elektroniczny** wybierz opcję **Dodaj** i wprowadź tabele wymagane do generowania włoskich faktur elektronicznych:

    - **Nazwa tabeli:** Arkusz faktur dla odbiorcy
    - **Nazwa tabeli:** Faktura projektu

3. Dla każdej tabeli zdefiniuj powiązany kontekst dokumentu:

    - W przypadku **Arkusza faktur dla odbiorcy** wybierz **Kontekst faktury dla odbiorcy**.
    - W przypadku **Faktury projektu** wybierz **Kontekst faktury projektu**.

![Konfigurowanie typów odpowiedzi.](media/e-Invoicing-services-get-started-ITA-Set-up-response-types.png)

## <a name="electronic-invoice-processing"></a>Przetwarzanie faktur elektronicznych

Podczas przetwarzania w Finance należy wykonać następujące zadania:

1. Generuj włoskie faktury e-fakturowane za pomocą Faktury elektroniczne
2. Wyświetl dzienniki wykonywania i przejrzyj wyniki przetwarzania

### <a name="generate-electronic-invoices"></a>Generuj faktury elektroniczne

Po włączeniu funkcji **Konfigurowalna integracja z Fakturami elektronicznymi** i aktywowaniu funkcji **IT00036** nie można już używać starego procesu Finance do generowania włoskich faktur elektronicznych. Zastępuje go nowym procesem o nazwie **Prześlij dokumenty elektroniczne**.

Dokumenty można przesyłać ręcznie na podstawie zapotrzebowania na dokumenty fakturowania elektronicznego.

> [!NOTE]
> Przed kontynuowaniem sprawdź, czy zostało zakończone wymagane ustawienie dla włoskich faktur elektronicznych. Aby uzyskać więcej informacji, zobacz [Faktury elektroniczne odbiorcy](./emea-ita-e-invoices.md). Należy pamiętać, że niektóre kroki konfiguracji opisane w tym temacie mogą być niedostępne z powodu aktywacji Faktur elektronicznych.

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Prześlij dokumenty elektroniczne**.
2. W przypadku pierwszego przesłania dokumentu należy w ustawieniu opcji **Ponowne przesłanie dokumentów** wybrać wartość **Nie**. Jeśli konieczne jest ponowne przesłanie dokumentu za pośrednictwem usługi, należy skonfigurować tę opcję na wartość **Ttak**.
3. Na skróconej karcie **Rekordy do uwzględnienia** wybierz opcję **Filtruj**, aby otworzyć okno dialogowe **Zapytania**, w którym można utworzyć kwerendę w celu wybrania dokumentów do przesłania.

![Przesyłanie dokumentów elektronicznych, okno dialogowe.](media/e-Invoicing-services-get-started-ITA-Submission-form.png)

#### <a name="filter-query"></a>Kwerenda filtra

1. W oknie dialogowym **Zapytania** skonfiguruj warunki filtrowania zarówno dla faktur sprzedaży, jak i faktury projektu, albo pozostaw te warunki puste, aby uwzględnić wszystkie nieprzesłane faktury.

    ![Konfigurowanie kryteriów filtru przesyłania.](media/e-Invoicing-services-get-started-ITA-Set-up-Submission-filter-criteria.png)

2. Kliknij przycisk **OK**, aby zamknąć okno dialogowe **Zapytania**.
3. Wybierz przycisk **OK**, aby przesłać wybrane dokumenty.

> ! [UWAGA] Podczas pierwszej próby przesłania dokumentu za pośrednictwem usługi zostaniesz poproszony o potwierdzenie połączenia z funkcją Faktury elektroniczne. Wybierz **Kliknij tutaj, aby połaczyć się się z usługą Elektronicznego przesyłania dokumentów**.

#### <a name="view-submission-logs"></a>Wyświetlanie dzienników przesyłania

Dzienniki przesyłania można wyświetlić dla wszystkich przesłanych dokumentów.

1. Przejdź do **Administrowanie organizacją \> Okresowe \> Dokumenty elektroniczne \> Dziennik przsyłania dokumentów elektronicznych**.
2. W polu **Typ dokumentu** wybierz opcję **Arkusz faktur dla odbiorcy** lub **Faktura projektu**, aby odfiltrować wymagane dokumenty elektroniczne.

    ![Wybór typu dokumentu, aby wyświetlić dzienniki przedłożenia.](media/e-Invoicing-services-get-started-ITA-Select-Document-type-for-viewing-submission-log.png)

    Wartość wyświetlana w kolumnie **Stan przesyłania** reprezentuje stan procesu przesyłania. Wskazuje on, czy proces został uruchomiony zgodnie z konfiguracją i czy jest wymagane wykonanie dodatkowych działań.

3. W okienku akcji wybierz **Zapytania \> Szczegóły przesyłania**, aby wyświetlić szczegóły dzienników wykonywania przesyłania.

    ![Wyświetlanie szczegółów dziennika przesyłania.](media/e-Invoicing-services-get-started-ITA-View-Submission-log-details.png)

4. Na skróconej karcie **Przetwarzanie akcji** można przejrzeć dziennik wykonywania akcji skonfigurowanych w wersji funkcji skonfigurowanej w RCS. Kolumna **Stan** wskazuje, czy akcja została pomyślnie uruchomiona.
5. Na skróconej karcie **Pliki akcji** można wyświetlać pliki pośrednie wygenerowane podczas wykonywania akcji. Można wybrać opcję **Widok**, aby pobrać wyjściowy plik XML w formacie **FatturaPA** i wyświetlić jego zawartość.

## <a name="related-topics"></a>Powiązane tematy

- [Omówienie fakturowania elektronicznego](e-invoicing-service-overview.md)
- [Rozpoczynanie pracy z fakturowaniem elektronicznym](e-invoicing-get-started.md)
- [Konfigurowanie fakturowania elektronicznego](e-invoicing-setup.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]