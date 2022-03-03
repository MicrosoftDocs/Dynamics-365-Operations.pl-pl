---
title: Obszar roboczy Automatyzacja faktur od dostawców
description: W tym temacie wyjaśniono, jak skonfigurować obszar roboczy, który jest powiązany z fakturami od dostawcy, oraz wyświetlić informacje dostępne w Microsoft Power BI.
author: abruer
ms.date: 02/14/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: twheeloc
ms.assetid: ''
ms.search.region: Global
ms.author: abruer
ms.search.validFrom: 2020-09-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: f28cc5f63df2f0d8a4c8cae407f7166aa4fa03db
ms.sourcegitcommit: 6102f70d4595d01b90afe5b23dfd8ec2ea030653
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/16/2022
ms.locfileid: "8182586"
---
# <a name="vendor-invoice-automation-workspace"></a>Obszar roboczy Automatyzacja faktur od dostawców

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

W tym temacie wyjaśniono, jak skonfigurować obszar roboczy, który jest powiązany z fakturami od dostawcy, oraz wyświetlić informacje dostępne w Microsoft Power BI. Informacje dotyczące faktury od dostawcy w tym obszarze roboczym są filtrowane dla określonych użytkowników i są wyświetlane w postaci graficznej.

## <a name="overview"></a>Omówienie

Obszar roboczy **Automatyzacja faktur od dostawców** zawiera informacje związane z przetwarzaniem faktur od dostawcy. Ten obszar roboczy zawiera widok **Moja praca** i stronę **Analizy - Wszystkie firmy**. Widok **Moja praca** zawiera kafelki podsumowań, siatki transakcji z dostawcami i informacje o odnośnych dostawcach. Strona **Analizy - Wszystkie firmy** wykorzystuje funkcje programu Power BI, aby pokazywać wizualizacje dotyczące faktur dla dostawców.

## <a name="set-up-the-workspace-to-show-power-bi-content"></a>Konfigurowanie obszaru roboczego do wyświetlania zawartości Power BI

Aby umożliwić wyświetlanie danych w wizualizacjach Power BI w obszarze roboczym **Automatyzacja faktur od dostawców**, należy ukończyć tę konfigurację.

1. W obszarze roboczym **Zarządzanie funkcjami** filtruj listę, aby znaleźć funkcję **Automatyzacji faktur od dostawców**.
3. Wybierz **Włącz teraz**.
4. Aby mieć pewność, że faktury mogą być przetwarzane od początku do końca bez konieczności ręcznej interwencji, należy skonfigurować przepływ pracy faktury od dostawcy. Aby skonfigurować przepływ pracy, wybierz kolejno opcje **Rozrachunki z dostawcami \> Ustawienia \> Przepływy pracy dla rozrachunków z dostawcami**.
5. Przejdź do **Rozrachunki z dostawcami \> Konfiguracja \> Parametry modułu rozrachunków z dostawcami** i wybierz kartę **Automatyzacja faktur od dostawców**, aby uzyskać więcej informacji, zajrzyj do [opcji konfiguracyjnych dotyczących automatyzacji faktur od dostawców](vnd-invoice-set-up-options.md).
6. Ustaw opcję **Automatyczne przesyłanie zaimportowanych faktur do systemu przepływu pracy** na **Tak**.
7. Jeśli dokumenty przyjęcia produktów powinny być dopasowywane automatycznie, dla opcji **Automatycznie dopasuj dokumenty przyjęcia produktów do wierszy faktur** należy wybrać opcję **Tak**.
8. Przejrzyj pozostałe, opcjonalne ustawienia i skonfiguruj je zgodnie z wymaganiami organizacji.
9. Otwórz **Administracja Systemu \> Konfiguracja \> Parametry Systemu** i ustaw pola **Walutę systemu** oraz **Kurs wymiany systemu**.
10. Otwórz **Księga ogólna \> Konfiguracja \> Księga** i ustaw pola **Waluta księgowa** oraz **Typ kursu wymiany**.
11. Przejdź do **Księga główna \> Waluty \> Kursy wymiany waluty** i wprowadź kursy wymiany między walutą transakcji a walutą rozliczeniową oraz między walutą rozliczeniową a walutą systemową.
12. Przejdź do **Administrowanie systemem \> Konfiguracja \> Magazyn jednostek** i wyszukaj **Środek automatyzacji faktur od dostawców**. Wybierz pozycję **Odśwież**.

Aby wyświetlić informacje wyświetlane w obszarze roboczym, należy mieć rolę zabezpieczeń Menedżer rozrachunków z dostawcami lub pracownik ds. rozrachunków z dostawcami.

## <a name="my-work-view"></a>Widok Moja praca

### <a name="company-selection"></a>Wybór firmy

Po włączeniu funkcji **Automatyzacja faktur od dostawców** pole **Firma** jest wyświetlane u góry obszaru roboczego. Wybór w polu **Firma** wpływa na wszystkie informacje wyświetlane w obszarze roboczym. Domyślnie w widoku są wyświetlane informacje o firmie, do której jest zalogowany użytkownik. Wybierając inną firmę w polu **Firma**, można wyświetlić informacje dotyczące firmy w obszarze roboczym systemu. Następnie możesz wybrać kafelek w obszarze roboczym, aby przejść do powiązanej strony w wybranej firmie.

### <a name="summary-tiles"></a>Kafelki podsumowania

Tabliczki w sekcji **Podsumowanie oczekujących faktur** w widoku **Moja praca** zawierają przegląd informacji o stanie faktur od dostawców. Można wyświetlić arkusze, które nie zostały jeszcze zaksięgowane i faktury, które zostały wstrzymane. Ponadto istnieją cztery tabliczki skojarzone z funkcją automatyzacji faktur od dostawcy:

- **Wymagane jest dopasowanie ręcznego dokumentu dostawy**
- **Nie powiodła się weryfikacja zgodności**
- **Faktury nie przesłane do przepływu pracy**
- **Niezaimportowane faktury**

(Te cztery kafelki wymagają włączenia funkcji automatyzacji faktur od dostawcy w module **Zarządzanie funkcjami**.)

Aby można było skorzystać z kafelka **Odzyskaj faktury od dostawcy**, funkcja musi być włączona w **parametrach modułu rozrachunków z dostawcami**. Przejdź do **Rozrachunki z dostawcami \> Parametry modułu rozrachunków z dostawcami**, a następnie na karcie **Faktura** określ opcję **Zezwalaj na zwrot faktury od dostawcy** na **Tak**.

Gdy funkcja jest włączona, trzy kafelki zostaną zgrupowane razem w obszarze roboczym w sekcji nazywanej **Arkuszami**. Kafelki to **Arkusze**, **Arkusze - przypisane do mnie** oraz **Pula faktur**. 

Informacje zawarte w sekcji **Podsumowanie oczekujących faktur** dotyczą firmy ustawionej jako firma domyślna w celu zarejestrowania się.

### <a name="creating-new-records"></a>Tworzenie nowego rekordu

Aby utworzyć nowy rekord faktury, wybierz opcję **Nowy**, a następnie wybierz jeden z następujących typów rekordów z listy:

- Faktura dostawcy
- Arkusz faktur
- Globalny arkusz faktur
- Rejestr faktur
- Zatwierdzenie faktury

Należy zwrócić uwagę, że utworzony rekord jest oparty na filtrze firmy, a nie w firmie, do której jest zalogowany użytkownik. Na przykład użytkownik jest zalogowany do firmy **UMSF**, ale filtr firmy jest ustawiany na **GBSI**. W takim przypadku po wybraniu opcji **Nowy**, a następnie wybraniu typu rekordu na liście, rekord jest tworzony w firmie GBSI.

### <a name="documents-not-invoiced-grids"></a>Niezafakturowane siatki dokumentów

Sekcja **Niezafakturowane dokumenty** zawiera siatki pokazujące dokumenty oczekujące na faktury od dostawcy.

W siatce **Otwarte zamówienia zakupu** są wyświetlane wszystkie zamówienia zakupu, które nie zostały jeszcze w pełni zafakturowane. Za pomocą przycisku **Wystaw fakturę teraz** można utworzyć fakturę od dostawcy dla zamówienia zakupu. Za pomocą przycisku **Wystaw fakturę przedpłaty teraz** można utworzyć fakturę przedpłaty dla zamówienia zakupu.

W siatce **Dokumenty przyjęcia produktów** są wyświetlane wszystkie dokumenty przyjęcia produktów, które nie zostały jeszcze w pełni zafakturowane. Za pomocą przycisku **Wystaw fakturę teraz** można utworzyć fakturę od dostawcy dla zamówienia zakupu.

Siatka **Oczekujących faktur od dostawcy** pokazuje wszystkie faktury od dostawców, które nie zostały przesłane do systemu przepływu pracy. Aby wyszukać określoną fakturę od dostawcy, można skorzystać z pola **Wyszukiwania** i/lub filtra firmy. Aby edytować transakcję wyświetlaną w siatce, można skorzystać z przycisku **Edycja**.

W siatce **Wyszukiwania zamówienia zakupu** za pomocą pola **Wyszukaj** można wyszukać określone zamówienie zakupu.

### <a name="related-information"></a>Informacje pokrewne

Informacje o zaksięgowanych fakturach można wyświetlić, korzystając z łączy znajdujących się po prawej stronie obszaru roboczego. Dotyczy to **Otwarte faktury dostawców**, **Arkusze faktur** i **Historia faktur i szczegóły ich uzgadniania**. W sekcji **Dostawcy** można uzyskać dostęp do filtrowanej listy, która pokazuje wszystkich zablokowanych dostawców, lub można skorzystać z łącza **Wszyscy dostawcy**. Dostępne są także łącza **Wszystkie zamówienia zakupu** i **Otwarte przedpłaty**.

### <a name="analytics--all-companies-page"></a>Analizy — Strona wszystkie firmy

Jeśli opcja **Automatyczne przesyłanie zaimportowanych faktur do systemu przepływu pracy** ma wartość **Tak** na stronie **Parametry rozrachunków z dostawcami**, możesz wyświetlić analizę automatyzacji. Na stronie **Analizy — wszystkie firmy** podano ważne metryki, takie jak faktury od dostawców, które są zatwierdzane przez osobę zatwierdzającą i przez firmę. Ta strona zawiera pięć stron raportów. Jedna strona zawiera przegląd, a pozostałe strony dostarczają szczegółowych informacji o miernikach automatycznych płatności w module Rozrachunki z dostawcami.

W poniższej tabeli pokazano wizualizacje dostępne na każdej stronie raportu.

| Strona raportu                    | Wizualizacje |
|--------------------------------|----------------|
| Omówienie faktury od dostawcy        | <ul><li>Oczekujące faktury od dostawcy w automatyzacji w walucie systemu</li><li>Faktury, których nie udało się zaimportować</li><li>Faktury w przepływie pracy</li><li>Faktury bezdotykowe są ważne 30 dni</li><li>Łączna liczba zautomatyzowanych faktur ostatnie 30 dni</li><li>Saldo otwartych faktur w walucie systemowej</li><li>Przyczyny niepowodzenia, ostatnie 30 dni</li><li>Procent zaksięgowanych faktur, które zostały przetworzone automatycznie</li><li>Dni na przetworzenie faktury</ul></li> |
| Stan automatyzacji              | <ul><li>Faktury bezdotykowe są ważne 30 dni</li><li>Faktury bezdotykowe są ważne 30 dni według firmy</li><li>Faktury bezdotykowe są ważne 30 dni według grupy dostawców</li><li>Procent zaksięgowanych faktur, które zostały przetworzone automatycznie</li><li>Dni na przetworzenie faktury</li></ul> |
| Faktury, których nie udało się zaimportować | <ul><li>Faktury, których nie udało się zaimportować</li><li>Faktury, których nie udało się zaimportować według firmy</li></ul> |
| Przyczyny niepowodzenia automatyzacji | <ul><li>Faktury zakończone niepowodzeniem</li><li>Faktury zakończone niepowodzeniem przez firmę</li><li>Faktury zakończone niepowodzeniem przez grupę dostawców</li></ul> |
| Stan przepływu pracy                | <ul><li>Faktury w przepływie pracy</li><li>Wystąpienia przepływu pracy faktur dla dostawców</li><li>Przypisanie na osobę zatwierdzającą</li><li>Przepływ pracy faktury od dostawcy na firmę</li><li>Średnia liczba dni w przepływie pracy wg osób zatwierdzających</li></ul> |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
