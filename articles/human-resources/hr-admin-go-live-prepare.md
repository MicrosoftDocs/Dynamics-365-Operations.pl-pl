---
title: Przygotowanie do rozpoczęcia eksploatacji Human Resources
description: Na tej stronie znajdują się wskazówki dotyczące sposobu przygotowania się do rozpoczęcia eksploatacji Dynamics 365 Human Resources.
author: rachel-profitt
manager: tfehr
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 59d7274c3b40e78209d90960c4514321b736876a
ms.sourcegitcommit: b40d6ce45aeb07724fc41d1a41923970b007fbcf
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/14/2020
ms.locfileid: "4420143"
---
# <a name="prepare-for-human-resources-go-live"></a>Przygotowanie do rozpoczęcia eksploatacji Human Resources

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób przygotowania się do korzystania z projektu Dynamics 365 Human Resources za pomocą Microsoft Dynamics Lifecycle Services (LCS). 

Ta grafika pokazuje etapy procesu przechodzenia do trybu na żywo. 

![Proces przechodzenia do trybu na żywo](./media/hr-admin-go-live-prepare-process.png)

W poniższej tabeli wymieniono wszystkie kroki procesu, oczekiwany czas trwania oraz osobę odpowiedzialną za akcję.

| Faza | Akcja | Czas trwania/godzina | Kto | Notatki |
| --- | --- | --- | --- |--- |
| 1 | Aktualizacja daty rozpoczęcia eksploatacji w LCS | Najpóźniej w ciągu 2-3 miesięcy | Partner/odbiorca | Daty punktów kontrolnych powinny być stale aktualizowane na bieżąco. |
| 2 | Zakończ i wyślij listę kontrolną | Kiedy testowanie akceptacji użytkownika (UAT) zostało ukończone | Partner/odbiorca | Postępuj zgodnie z instrukcjami przewidzianymi w [Ocena rozpoczęcia eksploatacji FastTrack](hr-admin-go-live-prepare.md#fasttrack-go-live-assessment). |
| 3 | Ocena projektu (FastTrack) | Architekt FastTrack* | Architekt dostarcza ocenę po otrzymaniu listy kontrolnej i kontynuuje przegląd, dopóki nie zostaną wyjaśnione pytania i są stosowane ograniczenia. |
| 4 | Warsztaty projektowe (FastTrack) | Architekt FastTrack* | |
| 5 | Importowanie pakietu danych | Zależy od projektu | Partner/odbiorca | Postępuj zgodnie z instrukcjami w [Omówienie zarządzania danymi](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/data-entities/data-entities-data-packages).|
| 6 | Gotowe do produkcji | Po ukończeniu wszystkich poprzednich kroków | Partner/odbiorca | Partner/odbiorca może przejąć kontrolę nad środowiskiem produkcyjnym.|
| 7 | Działania migracji | Zależy od projektu | Partner/odbiorca | |
| 8 | Rozpoczynanie eksploatacji | Zależy od projektu | Klient | |

> [!IMPORTANT]
> *Kroki 3 i 4 są wykonywane tylko dla odbiorców, którzy kwalifikują się do FastTrack.

## <a name="completing-the-lcs-methodology"></a>Kończenie metodologii usługi LCS

Głównym punktem kontrolnym w każdym projekcie implementacji jest migracja środowiska produkcyjnego. 

Aby zapewnić, że środowisko produkcyjne jest używane w operacjach na żywo, firma Microsoft postanowi o wystąpieniu produkcji tylko wtedy, gdy wdrożenie zbliża się do fazy **Działanie**, po ukończeniu wymaganych działań w metodologii usługi LCS. Aby uzyskać więcej informacji dotyczących środowisk w subskrypcji, zapoznaj się z  [Podręcznikiem systemu Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). 

Klienci muszą dokończyć **Analizę**, **Projektowanie i opracowywanie**, a następnie **Testować** etapy w metodologii usługi LCS, zanim zostanie udostępniony przycisk  **Konfiguruj** , który zażąda środowiska produkcyjnego. Aby zakończyć fazę w usługi LCS, należy najpierw ukończyć każdy wymagany krok w tej fazie. Po zakończeniu wszystkich etapów w fazie można zakończyć całą fazę. Można zawsze ponownie otworzyć fazę później, jeśli trzeba wprowadzić zmiany. Aby uzyskać więcej informacji, przejrzyj temat  [Lifecycle Services (LCS) dla klientów aplikacji Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/lifecycle-services/lcs-works-lcs). 

Proces wykonywania kroku składa się z dwóch części: 

- Należy wykonać pracę rzeczywistą, na przykład analizę zgodnego ze szczeliną lub test akceptacji użytkownika (UAT). 
- Zaznacz odpowiedni krok w metodologii usługi LCS jako zakończony. 

Dobrą praktyką jest wykonywanie kroków z metodologii w miarę postępów z implementacją. Nie należy czekać do ostatniej minuty. Nie należy po prostu klikać wszystkich kroków, aby można było korzystać z środowiska produkcyjnego. W najlepszym interesie klienta leży stosowanie stałej implementacji. 

## <a name="uat-for-your-solution"></a>UAT dla rozwiązania

Podczas fazy UAT należy przetestować wszystkie zaimplementowane procesy biznesowe oraz wszelkie dostosowania wprowadzone przez użytkownika w środowisku piaskownicy w projekcie implementacji. Aby zapewnić pomyślne wykonanie operacji, należy wziąć pod uwagę następujące kwestie, które należy wykonać w fazie UAT: 

- Przypadki testowe obejmują cały zakres wymagań. 
- Test za pomocą migrowanych danych. Dane te powinny zawierać dane główne, takie jak pracownicy, zadania i stanowiska. Należy również uwzględnić salda otwarcia, takie jak urlop i naliczenia nieobecności. Na koniec należy uwzględnić otwarte transakcje, takie jak bieżące rejestracje świadczeń. Zakończ testowanie ze wszystkimi typami danych, nawet jeśli zbiór danych nie został sfinalizowany. 
- Przetestuj za pomocą poprawnych ról zabezpieczeń (ról domyślnych i ról niestandardowych), które są przypisane do użytkowników. 
- Należy upewnić się, że rozwiązanie jest zgodne z dowolnymi wymogami przepisów prawnych obowiązującymi w firmie i w danym przemyśle. 
- Umożliwia dokumentowanie wszystkich funkcji oraz uzyskanie akceptacji i zarejestrowania od odbiorcy. 

## <a name="fasttrack-go-live-assessment"></a>Ocena rozpoczęcia eksploatacji FastTrack

Klienci posiadający kwalifikacje do FastTrack i korzystający z rozwiązania FastTrack Solution Architect ukończy ocenę rozpoczęcia eksploatacji z Microsoft FastTrack. Więcej informacji możesz przeczytać w  [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Około ośmiu tygodni przed przejściem na żywo, zespół FastTrack prosi o wypełnienie [Lista kontrolna czynności poprzedzających rozpoczęcie eksploatacji](https://go.microsoft.com/fwlink/?linkid=2146013).

Menedżer projektu lub członek projektu klucza musi wypełnić listę kontrolną czynności poprzedzających rozpoczęcie eksploatacji podczas fazy wstępnego tworzenia projektu. Zazwyczaj Lista kontrolna jest zakończona od czterech do sześciu tygodni przed zaproponowaną datą wejścia w życia, gdy UAT jest zakończone lub prawie zakończone. 

Po zakończeniu listy kontrolnej czynności poprzedzających rozpoczęcie eksploatacji wyślij ją pocztą e-mail do architekta rozwiązania FastTrack. Należy zawsze dołączać klucza pozostałego od klienta i partnera implementacji do wiadomości e-mail. 

Po przesłaniu listy kontrolnej architekt rozwiązań FastTrack dokona przeglądu projektu i przedstawi ocenę opisującą potencjalne ryzyko, najlepsze praktyki i zalecenia dotyczące pomyślnego uruchomienia projektu. W niektórych przypadkach architekt rozwiązania może wyróżnić współczynniki ryzyka i zapytać o plan zaradczy. 

## <a name="see-also"></a>Informacje dodatkowe

[Rozpoczynanie eksploatacji — często zadawane pytania](hr-admin-go-live-faq.md)