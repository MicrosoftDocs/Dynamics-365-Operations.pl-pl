---
title: Przygotowanie do rozpoczęcia eksploatacji Human Resources
description: Na tej stronie znajdują się wskazówki dotyczące sposobu przygotowania się do rozpoczęcia eksploatacji Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 2f6dbcbd92a99699ce8d7e91c1a7e89a6063035f
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5795148"
---
# <a name="prepare-for-human-resources-go-live"></a>Przygotowanie do rozpoczęcia eksploatacji Human Resources

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

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

Głównym punktem kontrolnym w każdym projekcie implementacji jest migracja środowiska produkcyjnego. Proces wykonywania kroku składa się z dwóch części: 

- Należy wykonać pracę rzeczywistą, na przykład analizę zgodnego ze szczeliną lub test akceptacji użytkownika (UAT). 
- Zaznacz odpowiedni krok w metodologii usługi LCS jako zakończony. 

Dobrą praktyką jest wykonywanie kroków z metodologii w miarę postępów z implementacją. Nie należy czekać do ostatniej minuty. W najlepszym interesie klienta leży stosowanie stałej implementacji. 

## <a name="uat-for-your-solution"></a>UAT dla rozwiązania

Podczas fazy UAT należy przetestować wszystkie zaimplementowane procesy biznesowe oraz wszelkie dostosowania wprowadzone przez użytkownika w środowisku piaskownicy w projekcie implementacji. Aby zapewnić pomyślne wykonanie operacji, należy wziąć pod uwagę następujące kwestie, które należy wykonać w fazie UAT: 

- Zalecamy, aby proces UAT rozpoczynał się w czystym i świeżym środowisku, w którym dane z konfiguracji GOLD są kopiowane do środowiska przed rozpoczęciem procesu UAT. Zalecamy używanie środowiska produkcyjnego jako środowiska GOLD do momentu uruchomienia, kiedy to środowisko stanie się produkcyjne.
- Przypadki testowe obejmują cały zakres wymagań. 
- Test za pomocą migrowanych danych. Dane te powinny zawierać dane główne, takie jak pracownicy, zadania i stanowiska. Należy również uwzględnić salda otwarcia, takie jak urlop i naliczenia nieobecności. Na koniec należy uwzględnić otwarte transakcje, takie jak bieżące rejestracje świadczeń. Zakończ testowanie ze wszystkimi typami danych, nawet jeśli zbiór danych nie został sfinalizowany. 
- Przetestuj za pomocą poprawnych ról zabezpieczeń (ról domyślnych i ról niestandardowych), które są przypisane do użytkowników. 
- Należy upewnić się, że rozwiązanie jest zgodne z dowolnymi wymogami przepisów prawnych obowiązującymi w firmie i w danym przemyśle. 
- Umożliwia dokumentowanie wszystkich funkcji oraz uzyskanie akceptacji i zarejestrowania od odbiorcy. 

## <a name="mock-go-live"></a>Symulacja rozpoczęcia

Przed rozpoczęciem pracy należy wykonać próbne uruchomienie, aby przetestować kroki wymagane do przełączenia ze starszych systemów na nowy system. Powinieneś przeprowadzić próbne uruchomienie w środowisku piaskownicy i uwzględnić wszystkie kroki w planie przełączania.

- Zalecamy używanie środowiska produkcyjnego jako środowiska konfiguracyjnego GOLD do momentu uruchomienia.
- Upewnij się, że masz silny proces zarządzania, aby chronić środowisko produkcyjne przed przypadkowymi transakcjami lub aktualizacjami przed uruchomieniem.
- Gdy wszystko będzie gotowe do użycia w trybie UAT lub podróży do pracy, odśwież środowisko piaskownicy ze środowiska produkcyjnego. Aby uzyskać więcej informacji, zobacz [Kopiowanie wystąpienia](hr-admin-setup-copy-instance.md).
- Przetestuj każdy etap planu przełączania w środowisku piaskownicy, a następnie zweryfikuj środowisko piaskownicy, wykonując wyrywkowe kontrole lub testy ze skryptów UAT w środowisku.
  - Testy powinny obejmować wszystkie migracje danych, w tym transformacje potrzebne do uruchomienia.
  - Ten proces powinien uwzględniać odcięcie praktyk w przypadku starszych systemów.
  - Pamiętaj, aby uwzględnić wszystkie etapy przełączania integracji lub kroki systemu zewnętrznego w przełączaniu próbnym.
- Jeśli zauważysz jakiekolwiek problemy podczas próbnego przełączania, może być wymagane drugie cięcie próbne. Z tego powodu zalecamy zaplanowanie dwóch próbnych zmian w planie projektu.

## <a name="fasttrack-go-live-assessment"></a>Ocena rozpoczęcia eksploatacji FastTrack

Klienci posiadający kwalifikacje do FastTrack i korzystający z rozwiązania FastTrack Solution Architect ukończy ocenę rozpoczęcia eksploatacji z Microsoft FastTrack. Więcej informacji możesz przeczytać w  [Microsoft FastTrack](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/fasttrack-dynamics-365-overview). 

Około ośmiu tygodni przed przejściem na żywo, zespół FastTrack prosi o wypełnienie [Lista kontrolna czynności poprzedzających rozpoczęcie eksploatacji](https://go.microsoft.com/fwlink/?linkid=2146013).

Menedżer projektu lub członek projektu klucza musi wypełnić listę kontrolną czynności poprzedzających rozpoczęcie eksploatacji podczas fazy wstępnego tworzenia projektu. Zazwyczaj Lista kontrolna jest zakończona od czterech do sześciu tygodni przed zaproponowaną datą wejścia w życia, gdy UAT jest zakończone lub prawie zakończone. 

Po zakończeniu listy kontrolnej czynności poprzedzających rozpoczęcie eksploatacji wyślij ją pocztą e-mail do architekta rozwiązania FastTrack. Należy zawsze dołączać klucza pozostałego od klienta i partnera implementacji do wiadomości e-mail. 

Po przesłaniu listy kontrolnej architekt rozwiązań FastTrack dokona przeglądu projektu i przedstawi ocenę opisującą potencjalne ryzyko, najlepsze praktyki i zalecenia dotyczące pomyślnego uruchomienia projektu. W niektórych przypadkach architekt rozwiązania może wyróżnić współczynniki ryzyka i zapytać o plan zaradczy. 

## <a name="see-also"></a>Informacje dodatkowe

[Rozpoczynanie eksploatacji — często zadawane pytania](hr-admin-go-live-faq.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]