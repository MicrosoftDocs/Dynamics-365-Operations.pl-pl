---
title: Konfigurowanie integracji Attract z serwisem LinkedIn — często zadawane pytania
description: Ten temat zawiera odpowiedzi na pytania, które mogą być związane z integracją między serwisem LinkedIn i aplikacją Microsoft Dynamics 365  Talent - Attract.
author: hasrivas
manager: AnnBe
ms.date: 07/08/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: hasrivas
ms.search.validFrom: 2019-07-08
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: d66ebc01597f8038a38b46a9f1b70feaa5dc505e
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2008646"
---
# <a name="linkedin-integration-faq"></a>Integracja z serwisem LinkedIn — często zadawane pytania

[!include [banner](includes/banner.md)]

LinkedIn to największa ogólnoświatowa sieć profesjonalistów. Microsoft Dynamics Talent: Attract zostaje zintegorwany z serwisem LinkedIn, aby uzyskać dostęp do najlepszych talentów całego świata. Attract umożliwia publikację ofert pracy bezpośrednio w serwisie LinkedIn i umożliwia także uzyskiwanie informacji o kandydacie z serwisu LinkedIn do Attract.

## <a name="for-recruiters-and-hiring-managers"></a>Dla rekrutacji i kierowników rekruterów

Poniżej znajdują się odpowiedzi na często zadawane pytania dotyczące sposobu korzystania z funkcji attract i serwisu LinkedIn

### <a name="what-linkedin-features-do-i-get-with-attract"></a>Jakie funkcje serwisu LinkedIn można otrzymać w Attract?

Integracja Attract z usługą LinkedIn umożliwia wykonywanie następujących zadań:

- [Publikację ofert pracy w serwisie LinkedIn](./attract-post-jobs-to-linkedin.md) (jako listy bezpłatne).
- [Eksport informacji o kandydatach z serwisu LinkedIn do Attract](./attract-linkedin-recruiter.md#export-linkedin-candidates-to-attract-with-one-click).
- [Zezwalanie kandydatom na aplikację na stanowiska pracy w serwisie LinkedIn](./attract-admin-linkedin.md#set-up-apply-with-linkedin-in-attract)

### <a name="what-do-i-need-before-i-can-post-jobs-to-linkedin"></a>Co jest potrzebne, aby można było publikować oferty pracy w serwisie LinkedIn?

Administrator musi [skonfigurować integrację LinkedIn w Attract](./attract-admin-linkedin.md#configure-job-posting-to-linkedin). Po wykonainiu tych kroków, możesz zaczynać.

### <a name="how-do-i-post-jobs-to-linkedin-from-attract"></a>Jak można publikować ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract?

Po utworzeniu oferty pracy w Attract, wystarczy wybrać przycisk **Opublikuj teraz**, który odpowiada serwisowi LinkedIn. Aby uzyskać więcej informacji, przeczytaj [Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract](./attract-post-jobs-to-linkedin.md#post-jobs-to-linkedin).

### <a name="can-i-get-candidate-information-from-linkedin-into-attract"></a>Czy mogę uzyskać informacje o kandydacie z LinkedIn w Attract?

Tak. Jeśli zobaczysz dobrego kandydata w serwisie LinkedIn, możesz łatwo wyeksportować informacje na temat tego kandydata do Attract. Aby uzyskać więcej informacji, zobacz [Pozyskiwanie kandydatów za pomocą usługi LinkedIn Recruiter](attract-linkedin-recruiter.md).

### <a name="how-can-i-get-help-accessing-linkedin-from-attract"></a>W jaki sposób można uzyskać pomoc na temat używania serwisu LinkedIn za pomocą Attract?

Jeśli występują problemy z logowaniem się lub publikacją ofert pracy w serwisie LinkedIn przy pomocy Attracy, przejrzyj informacje [Rozwiązywanie problemów z integracją z serwisem LinkedIn](./attract-troubleshoot-linkedin.md).

Aby poznać inne problemy z Attract, zapoznaj się z tematem [Uzyskiwanie pomocy technicznej dotyczącej rozwiązania Talent](./talent-support.md). Aby uzyskać pomoc dotyczącą serwisu LinkedIn, zobacz [Pomoc techniczna serwisu LinkedIn](https://www.linkedin.com/help).

## <a name="for-admins-and-developers"></a>Dla administratorów i deweloperów

Poniżej znajdują się odpowiedzi na często zadawane pytania dotyczące sposobu konfiguracji integracji Attract z LinkedIn.

### <a name="how-do-i-configure-attract-so-that-recruiters-and-hiring-managers-can-post-jobs-to-linkedin"></a>Jak skonfigurować Attract, aby umożliwić rekruterom i menedżerom zatrudniania publikację ofert pracy w serwisie LinkedIn?

Obie opcje konfiguruje się na karcie **Integracja z serwisem LinkedIn** w centrum administracyjnym. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji z serwisem LinkedIn](./attract-admin-linkedin.md).

### <a name="can-i-export-candidate-information-from-linkedin"></a>Czy mogę eksportować informacje o kandydatach z serwisu LinkedIn do Attract?

Tak, ale najpierw należy skonfigurować integrację z LinkedIn Recruiter. Aby uzyskać więcej informacji, zobacz [Konfigurowanie integracji z serwisem LinkedIn](./attract-admin-linkedin.md).

### <a name="how-can-i-post-jobs-to-premium-job-slots-on-linkedin"></a>Jak można publikować oferty pracy w publikacjach ofert pracy premium w serwisie LinkedIn?

Chociaż Attract pozwala na wydajne rozwiązanie do publikacji ofert pracy w serwisie LinkedIn, konieczne może okazać się uzyskanie dodatkowej elastyczności. Można na przykład publikować oferty pracy premium, oprócz list bezpłatnych, lub można też chcieć, aby serwis LinkedIn przetwarzał zadania wsadowe ofert pracy więcej niż raz dziennie.

#### <a name="types-of-linkedin-job-posts"></a>Typy ogłoszeń w serwisie LinkedIn

W serwisie LinkedIn są dostępne następujące typy publikacji ofert pracy:

- **Lista z ograniczeniami** — bezpłatna publikacja ofert pracy wyświetlanyche w wynikach wyszukiwania, gdy kandydaci szukają pracy w serwisie LinkedIn oraz na stronie firmy w LinkedIn. Listy z ograniczeniami są ukierunkowane na aktywne osoby poszukujące pracy. Ten typ listy jest typem, który Attract oferuje do serwisu LinkedIn. Nie możesz promować list z ograniczeniami w serwisie LinkedIn. Jeśli chcesz promować listy z ograniczonymi, musisz pracować z serwisem LinkedIn, aby włączyć zawijanie zadań. Aby uzyskać więcej informacji na temat zawijania zadań, zapoznaj się z [Miejsca na zadania z ograniczoną oferta a miejsca na zadania premium w kontekście zawijania zadań](https://www.linkedin.com/help/recruiter/answer/79049/limited-listings-vs-premium-job-slots-for-job-wrapping) i [Zawijanie zadań — często zadawane pytania](https://www.linkedin.com/help/recruiter/answer/79050/job-wrapping-frequently-asked-questions).
- **Miejsca na zadania premium** — zakupione wpisy, które znajdują się w różnych miejscach w serwisie LinkedIn, takich jak feed serwisu LinkedIn, wiadomości E-mail i **Oferty pracy, które mogą cię zainteresować**. Miejsca na zadania premium są ukierunkowane na kandydatów pasywnych, ale są również wyświetlane w wyszukiwaniu zadań.

Attract publikuje oferty pracy w LinkedIn jako listy bezpłatne. Jeśli mają być używane miejsca na zadania premium, należy użyć funkcji zawijania zadań w LinkedIn Recruiter. Zawijanie zadań wymaga kontraktu zawijania zadań z serwisem LinkedIn. Aby uzyskać więcej informacji, zobacz temat [Zawijanie zadań w LinkedIn Recruiter - Omówienie](https://www.linkedin.com/help/recruiter/answer/79037).

#### <a name="frequency-of-batch-processing-on-linkedin"></a>Częstotliwość przetwarzania wsadowego w serwisie LinkedIn

Serwis LinkedIn przetwarza opublikowane prace w partii przez Attract raz dziennie. W związku z tym może upłynąć nawet do 48 godzin, aby prace były wyświetlane w serwisie LinkedIn po publikacji ich przez Attract. Jeśli chcesz, aby zadania były wyświetlane wcześniej w serwisie LinkedIn, lub jeśli potrzebujesz dodatkowej elastyczności, możesz skorzystać z interfejsu API programu rekrutacji z serwisu LinkedIn. Aby uzyskać więcej informacji, zobacz [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect).

#### <a name="table-of-options-for-job-posting-to-linkedin"></a>Tabela opcji publikacji ofert pracy w serwisie LinkedIn

W poniższej tabeli opisano różne opcje publikacji ofert pracy w serwisie LinkedIn. Zawiera zalety każdej opcji oraz dodatkowe informacje.

|  | Attract | Zawijanie zadań przez LinkedIn Recruiter | Recruiter System Connect interfejs API |
|---|---|---|---|
| **Opis** | Attract publikuje oferty pracy w LinkedIn jako przepływ danych XML. | Kontrakty firmy z serwisem LinkedIn i udostępnia przepływ danych XML służący do publikacji ofert pracy. | Klient korzysta z interfejsu API w celu synchronizowania informacji między Attract a LinkedIn Recruiter. |
| **Jaki typ ofert pracy można publikować?** | Lista z ograniczeniami | Miejce na zadanie premium lub lista z ograniczeniami | Lista z ograniczeniami |
| **Czy można promować ofertę pracy w serwisie LinkedIn?** | Nie | Miejsce na zadanie premium: tak<br>Lista z ograniczeniami: nie | Nie |
| **Jak często oferty są publikowane w serwisie LinkedIn?** | Raz dziennie | Raz dziennie | Wiele razy dziennie, zgodnie z definicją interfejsu API |
| **Zalecane przez serwis LinkedIn?** | Nie | Tak | Nie |
| **Czego potrzebuję?** | Zakup aplikacji Attract | Zadanie pakowania umowy z serwisem LinkedIn i zakupem dodatkowych gniazd zadań | Umowa API z usługą LinkedIn | 
| **Gdzie można znaleźć więcej informacji?** | [Konfigurowanie integracji z serwisem LinkedIn](./attract-admin-linkedin.md) | [Zawijanie zadań przez LinkedIn Recruiter - Omówienie](https://www.linkedin.com/help/recruiter/answer/79037) | [Recruiter System Connect](https://docs.microsoft.com/linkedin/talent/recruiter-system-connect) |

> [!NOTE]
> Do publikacji ofert pracy w usłudze LinkedIn za pomocą Attract nie jest potrzebna licencja LinkedIn Recruiter System Connect.

## <a name="see-also"></a>Informacje dodatkowe

[Konfigurowanie integracji z serwisem LinkedIn](./attract-admin-linkedin.md)

[Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Attract](./attract-post-jobs-to-linkedin.md)

[Pozyskiwanie kandydatów za pomocą usługi LinkedIn Recruiter](./attract-linkedin-recruiter.md)

[Rozwiązywanie problemów integracji z serwisem LinkedIn](./attract-troubleshoot-linkedin.md)
