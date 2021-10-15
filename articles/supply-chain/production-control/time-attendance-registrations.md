---
title: Omówienie rejestracji czasu i frekwencji
description: Pracownicy odpowiedzialni za rejestrację czasu mogą wprowadzać różne zdarzenia, na przykład wejścia, wyjścia, działania pośrednie i nieobecności. W tym temacie opisano rejestracje, ich obliczanie i zatwierdzanie, a także stosowanie przepływu pracy w celu dodania struktury i automatycznego zatwierdzania do procesu zatwierdzania kart czasu pracy.
author: johanhoffmann
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmWorker, JmgCalcApprovePickDialog, JmgGroupApprove, JmgGroupCalc, JmgGroupSigningTable, JmgRegistration, JmgTimeCalcParmeters, WorkflowTableListPageRnr, JmgRegistrationSetup, JmgStampTrans, JmgStampJournalTrans
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "53351"
- intro-internal
ms.assetid: 885b0cdf-53d7-4cb4-92fe-da1b9e32b39f
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0755a22365a2fdcbc6ed06c7e85c47d86808912e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7567974"
---
# <a name="time-and-attendance-registration-overview"></a>Omówienie rejestracji czasu i frekwencji

[!include [banner](../includes/banner.md)]

Pracownicy odpowiedzialni za rejestrację czasu mogą wprowadzać różne zdarzenia, na przykład wejścia, wyjścia, działania pośrednie i nieobecności. W tym temacie opisano rejestracje, ich obliczanie i zatwierdzanie, a także stosowanie przepływu pracy w celu dodania struktury i automatycznego zatwierdzania do procesu zatwierdzania kart czasu pracy.

## <a name="registrations"></a>Rejestracje

W firmach używających modułu Czas i frekwencja pracownicy muszą rejestrować czas spędzany w pracy i obecność. W niektórych firmach może być wymagane rejestrowanie i wyrejestrowywanie pracowników. W innych firmach pracownicy również mogą rejestrować zużycie czasu na realną pracę i na przerwy w pracy. Dla kogo jest przeznaczony moduł Czas i frekwencja:

- Pracownicy, którzy muszą regularnie rejestrować czas i obecność, np. codziennie, co tydzień lub co dwa tygodnie.
- Przełożeni, menedżerowie i dyrektorzy ds. listy płac, którzy obliczają, zatwierdzają i przenoszą rejestracje pracownia do dalszego przetwarzania.

| **Uwaga**                                                                                                                                                                                                                                                    |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Po uruchomieniu modułu Czas i frekwencja wraz z modułem Uruchomieniem produkcji wszystkie rejestracje w tych projektach, działania w ramach projektów, działania bezpośrednie, kody nieobecności oraz nadgodziny i elastyczny czas pracy są używane do obliczania listy płac w obu tych modułach. |

## <a name="time-registrations-workers"></a> Pracownicy odpowiedzialni za rejestrację czasu

Aby można było zarejestrować czas i nieobecności, należy skonfigurować pracowników jako pracowników odpowiedzialnych za rejestrację czasu w firmie, w której są zatrudnieni.

Po zakończeniu instalacji pracownicy mogą wprowadzać różnego typu rejestracje.

- Rejestrowanie i wyrejestrowywanie się po przyjściu lub przy wyjściu z pracy.
- Zużycie czasu i pozycji dotyczących zadań produkcji.
- Czas przeznaczony na komputerze w wydziale produkcyjnym, jeśli komputer został zdefiniowany jako zasób.

| **Uwaga**                                                                                                                                                                                                                      |
|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Pracownikowi można automatycznie przypisać rejestracje czasu, które są wykonywane na określonym komputerze w dziale produkcyjnym, jeśli pracownik wybierze rolę Asystent do komputera podczas rozpoczynania zadania produkcji. |

- Rejestracje czasu na projekty i działania projektów.
- Rejestrowanie opłat w projekcie i zużycia towarów przy użyciu odpowiednich arkuszy opłat projektu i arkuszy pozycji projektu.
- Planowana nieobecność.
- Nieobecność w przypadku spóźnienia do pracy lub wcześniejszego wyjścia.
- Przerwy w pracy wprowadzone ręcznie lub obliczone automatycznie przez system.
- Działania pośrednie, które są niepłatnymi działaniami podejmowanymi przez pracownika w ciągu dnia roboczego. Do takich działań należą spotkania lub sprzątanie stanowiska pracy.
- Nadgodziny, które mogą być rejestrowane jako dodatkowe godziny, elastyczny czas pracy lub praca w nadgodzinach.

## <a name="adding-clock-out-registrations"></a>Dodawanie rejestracji wyrejestrowania

Jeśli pracownik zapomni się wyrejestrować po zakończeniu dnia pracy, brakująca rejestracja zostanie dodana przy uruchomieniu zadania wsadowego. System porówna godzinę zarejestrowania z godziną wyrejestrowania zgodnie z profilem przypisanym do pracownika, a następnie automatycznie wstawi brakujące wyrejestrowanie, tak aby pasowało do końca dnia roboczego profilu. Rejestracja zarejestrowania i wyrejestrowania są istotne dla kolejnych obliczeń i zatwierdzania rejestracji czasu, zanim mogą zostać przeniesione do listy płac.

## <a name="calculating-registrations"></a>Obliczanie rejestracji

Jeśli pracownik odpowiedzialny za rejestrację czasu ma przypisaną grupę obliczania, która zazwyczaj odnosi się do określonego zespołu, zmiany lub grupy roboczej. Menedżer lub przełożony zwykle sprawdza rejestracje dokonane przez pracowników i dlatego jest on osobą odpowiedzialną za codzienne obliczenia dla odpowiednich grup obliczeń. W ramach procesu obliczania menedżer zespołu lub przełożony zwykle może:

- Poprawiać błędne rejestracje. Na przykład zmieniać kody przełączania i korygować informacje zwrotne o zadaniach produkcyjnych.
- Dodawać brakujące rejestracje. Na przykład tworzyć rejestracje wyrejestrowania i tworzyć transakcje nieobecności.
- Usuwać nieprawidłowe rejestracje.

Ponieważ zarejestrowany czas musi pasować do profilu czasu pracownika przed obliczeniem rejestracji, trzeba zastąpić profil czasu pracy dla dowolnego pracownika, dla którego obowiązuje wyjątek dla standardowego czasu pracy. W przypadku gdy profilem pracownika jest dzienna zmiana robocza, a pracownik zgodził się pracować na nocnej zmianie bez zapłaty za nadgodziny, menedżer zespołu lub przełożony musi zastąpić domyślny profil pracownika, by obliczyć czas pracownika według stawki standardowej, a nie za nadgodziny. Oprócz tego w obliczeniu pojawi się również błąd, jeśli nie będzie rejestracji nieobecności. Trzeba ją dodać, aby dało się wykonać obliczenie.

## <a name="approving-registrations"></a>Zatwierdzanie rejestracji

Tak samo jak przy przypisywaniu grupy obliczania do pracownika odpowiedzialnego za rejestrowanie czasu, trzeba również przypisać grupę zatwierdzania. Zazwyczaj grupa będzie przypisana do zespołu, zmiany lub grupy roboczej. Należy zatwierdzić rejestracje czasu, które zostały obliczone poprawnie — czyli wykonać obliczenia bez błędów — zanim będzie można wygenerować elementy, które później mogą zostać przetransferowane na system listy płac. Rejestracje zazwyczaj zatwierdza administrator listy płac i przed zatwierdzeniem może on:

- Zastąpić umowy płatności dla poszczególnych pracowników.
- Dodawać dodatki ręczne.
- Wprowadzania dodatkowe informacje rejestracje nieobecności.

| **Uwaga**                                                                                                                                                                             |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Jeśli dla konkretnych pracowników obliczono nadgodziny, można je zaalokować do konkretnych zadań wykonywanych podczas dnia. Ma to znaczenie w przypadku, gdy koszty pracy są obliczane na podstawie płacy pracownika. |

## <a name="approving-registrations-using-workflow"></a> Zatwierdzanie rejestracji za pomocą przepływu pracy

Można ustawić proces zatwierdzania przepływu pracy, który automatycznie zatwierdza rejestracje zgodnie z regułami przepływu pracy, pozostawiając do ręcznej obsługi tylko odchylenia. Po aktywowaniu zatwierdzenia przepływu pracy menedżer zespołu lub przełożony przesyła obliczone rejestracje do zatwierdzenia. Proces przepływu pracy wygeneruje odpowiednie zatwierdzenia i zadania, a następnie przypisze je do odpowiednich użytkowników i ról jako zidentyfikowane w przepływie pracy. Dla modułu Czas i frekwencja dostępne są dwa zatwierdzenia przepływu pracy.

| System Workflow                                  | Cel                                                                                                   | Typ rejestracji                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Suma dni w module Czas i obecność            | Przepływ pracy sprawdza poprawność rejestracji względem na przykład oczekiwanej liczby godzin w dniu. |                                                                                                                                                                                                                                                       |
| Rejestracja dziennika w module Czas i obecność. | Przepływ pracy sprawdza poprawność każdego typu rejestracji dla daty rejestracji.                           | Czas i obecność • Wejście • Wyjście • Nieobecność • Przerwa • Kod przełączania • Projekt • Działanie projektu • Działanie pośrednie • Zadania produkcyjne • Oczekiwanie przed • Ustawienia • Proces • Nakładanie • Transport • Oczekiwanie po • Rozpocznij asystę • Zakończ asystę |

## <a name="transferring-approved-registrations"></a>Przesyłanie zatwierdzonych rejestracji

Po zatwierdzeniu rejestracji można przenieść je do okresowego zadania listy płac. Przeniesiona rejestracja jest księgowana jako działanie lub zadanie, do którego się odwołuje, zlecenie produkcyjne lub projekt. Transakcje listy płac są generowane dla każdego pracownika na podstawie rejestracji.  

## <a name="reversing-transferred-registrations"></a>Wycofywanie przeniesionych rejestracji

Transakcje można wycofać do czasu uruchomienia przekazania płatności dla listy płac. To oznacza, że dane listy płac zostały przeniesione do zewnętrznego pliku. Po wycofaniu rejestracji wszelkie transakcje zaksięgowane dla zleceń produkcyjnych lub projektów zostają zaksięgowane przeciwstawnie i tym samym zneutralizowane.

| **Uwaga**                                                 |
|----------------------------------------------------------|
| Zewnętrzny plik możne zostać zaimportowany do systemu listy płac. |

## <a name="registrations-in-electronic-timecards"></a>Rejestracje na elektronicznych kartach czasowych

Pracownicy z obowiązkami, które nie wymagają natychmiastowej reakcji, tak jak ma to miejsce w przypadku zadań produkcji, ale którzy wykonują działania związane z projektami, mogą korzystać z elektronicznych kart czasowych. Elektroniczne karty czasowe pozwalają wprowadzać rejestracje w najwygodniejszy sposób dla harmonogramu działania firmy — codziennie, co tydzień lub kiedy pracownik wróci do biura. Aby używać tych kart czasowych lub tych pracowników, musisz włączyć opcję „Użyj karty czasowej” w szczegółach pracownika. Elektroniczne karty czasowe pozwalają pracownikowi rejestrować następujące dane:

- Data
- Typ rejestracji
- Odwołanie zadania — takie jak projekt, zlecenie produkcyjne lub działanie bezpośrednie
- Identyfikator zadania
- Zużycie czasu
- Opłaty w ramach projektu
- Towary w ramach projektu

[!INCLUDE[footer-include](../../includes/footer-banner.md)]