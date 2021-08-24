---
title: Rozpoczynanie eksploatacji — często zadawane pytania
description: Ten temat zawiera listę często zadawanych pytań dotyczących sposobu przychodzenia do projektu implementacji Dynamics 365 Human Resources.
author: rachel-profitt
ms.date: 10/13/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: raprofit
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: ca6c89f5f6dc4660a77587112526a6516f683f64ce95a9a83f39add119d2ee12
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/05/2021
ms.locfileid: "6731402"
---
# <a name="go-live-faq"></a>Rozpoczynanie eksploatacji — często zadawane pytania 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Ten temat zawiera listę często zadawanych pytań dotyczących sposobu przychodzenia do projektu implementacji Dynamics 365 Human Resources. 

## <a name="when-can-i-configure-and-request-my-production-environment"></a>Kiedy mogę skonfigurować i zażądać mojego środowiska produkcyjnego? 

Zazwyczaj środowisko produkcyjne jest wdrażane po spełnieniu następujących kryteriów:

- Wszystkie dostosowania są wykonane w kodzie.
- Testowanie akceptacji użytkownika (UAT) zostało ukończone.
- Odbiorca wylogował się z rozwiązania.
- Brak problemów z blokowaniem dla rozwiązania „Live”. 

Gdy zakwalifikowani odbiorcy znajdują się na tym etapie, zespół Microsoft FastTrack będzie współpracować z zespołem projektu w celu wykonania oceny. 

## <a name="what-are-the-prerequisites-to-deploying-a-production-environment"></a>Jakie są wymagania wstępne dotyczące wdrażania środowiska produkcyjnego? 

Aby zapoznać się z listą wymagań wstępnych, przejrzyj temat  [Przygotowywanie do rozpoczęcia eksploatacji](hr-admin-go-live-prepare.md). 

## <a name="what-is-a-go-live-assessment"></a>Co to jest Ocena rozpoczęcia eksploatacji?  

Ocena rozpoczęcia eksploatacji jest częścią  [programu Microsoft FastTrack](/dynamics365/fasttrack/). Podczas tego przeglądu architekt rozwiązania ocenia, czy projekt implementacji jest gotowy do pomyślnej migracji i przejścia do rozpoczęcia eksploatacji. Ten przegląd jest wymagany dla każdego projektu implementacji, zanim będzie można zażądać jego wdrożenia w środowisku produkcyjnym. 

## <a name="our-sandbox-environments-are-deployed-in-the-central-us-datacenter-we-want-our-production-environments-to-be-deployed-in-the-west-us-datacenter-can-i-select-west-us-as-the-datacenter-in-my-production-configuration"></a>Nasze środowiska piaskownicy są wdrażane w centrum danych w środkowych Stanach Zjednoczonych. Chcemy, aby nasze środowiska produkcyjne były wdrażane w centrum danych w zachodnich Stanach Zjednoczonych. Czy mogę wybrać Zachodnie stany USA jako centrum danych w mojej konfiguracji produkcyjnej? 

USŁUGI LCS nie ogranicza wyboru innego centrum danych podczas wdrażania środowiska Human Resources, ale zdecydowanie zaleca się, aby nie wybierać innego centrum danych.  

Jeśli chcesz, aby środowisko produkcyjne znajdowało się w centrum danych w zachodnich Stanach Zjednoczonych, najpierw należy ponownie wdrożyć środowiska piaskownicy w centrum danych w zachodnich Stanach Zjednoczonych, przetestować je i się wylogować. 

Aby uzyskać informacje dotyczące wyboru odpowiedniego centrum danych, zapoznaj się z [Wymaganiami sieciowymi](../fin-ops-core/fin-ops/get-started/system-requirements.md#network-requirements). 

## <a name="what-level-of-access-do-i-have-to-the-azure-resources-for-my-human-resources-environments"></a>Jaki poziom dostępu muszę posiadać do zasobów systemu Azure dla środowisk z Human Resources?  

Dostęp do środowisk Human Resources jest ograniczony. Nie możesz uzyskać dostępu do maszyny wirtualnej (VM) ani Microsoft Internet Information Services (IIS). Nie można również uzyskać dostępu do bazy danych za pośrednictwem programu Management Studio Microsoft SQL Server. 

Chociaż nie możesz uzyskać bezpośredniego dostępu do zasobów platformy Azure lub środowiska Dynamics 365 Human Resources, istnieją dodatkowe funkcje, których możesz użyć, aby uzyskać dostęp do swoich danych:

- Bazę danych SQL Azure można wdrożyć we własnej dzierżawie Azure i za pomocą funkcji Używanie własnej bazy danych w celu zsynchronizowania danych. Aby uzyskać więcej informacji, zapoznaj się z tematem [Dobierz własną bazę danych (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md).

- Funkcji integracji Dataverse można wykorzystywać do synchronizowania wybranych jednostek w bazie danych Dataverse. Aby uzyskać więcej informacji, zobacz [Tabele Dataverse](hr-developer-entities.md). 

## <a name="how-often-is-my-production-database-backed-up"></a>Jak często jest wykonywana kopia zapasowa bazy danych produkcji? 

Automatyczne wykonywanie kopii zapasowych baz danych jest chronione przy użyciu następujących częstotliwości:

| Typ kopii zapasowej | Częstotliwość |
| --- | --- |
| Tworzenie pełnej kopii zapasowych bazy danych | Tygodniowa |
| Różnicowa kopia zapasowa bazy danych | Co 12-24 godzin |
| Kopia zapasowa dziennika transakcji | Co 5 do 10 minut |

Firma Microsoft zachowuje wystarczające kopie zapasowe, aby umożliwić przywracanie bazy danych do punktu w czasie (PITR) z ostatnich 14 dni. 

Aby uzyskać więcej informacji, zobacz  [Więcej informacji na temat automatycznego wykonywania kopii zapasowych bazy danych SQL](/azure/azure-sql/database/automated-backups-overview?tabs=single-database). 

## <a name="can-i-request-a-copy-of-the-backup-of-my-production-database"></a>Czy mogę zażądać kopii kopii zapasowej bazy danych produkcji? 

Nr Można jednak przesłać żądanie usługi odświeżania bazy danych w celu skopiowania środowiska produkcyjnego do środowiska piaskownicy. Bazę danych SQL Azure można wdrożyć we własnej dzierżawie Azure i za pomocą funkcji Używanie własnej bazy danych w celu zsynchronizowania danych ze środowiska produkcyjnego. Aby uzyskać więcej informacji, zapoznaj się z tematem [Dobierz własną bazę danych (BYOD)](../fin-ops-core/dev-itpro/analytics/export-entities-to-your-own-database.md). 

## <a name="how-do-i-move-my-sandbox-environment-to-production-for-go-live"></a>Jak przenieść środowisko piaskownicy do produkcji, aby rozpocząć eksploatację? 

Ponieważ funkcja kopiowania nie jest dostępna w celu przeniesienia środowiska z piaskownicy do środowiska produkcyjnego, należy skorzystać z pakietów danych w celu przeniesienia danych do środowiska produkcyjnego.  

Zalecamy obsługiwanie jasnej listy jednostek skonfigurowanych w obszarze izolowanym w całym projekcie. Następnie przetestuj proces migracji i migracji wszystkich pakietów danych potrzebnych do tego celu. Wszystkie pakiety danych trzeba przenieść ręcznie do środowiska produkcyjnego, gdy będzie gotowe do pracy. 

## <a name="what-should-i-do-if-my-production-environment-is-down"></a>Co należy zrobić, jeśli środowisko produkcyjne jest wyłączone? 

Aby zgłosić awarię środowiska produkcji, należy wykonać proces opisany w temacie  [Zgłaszanie awarii produkcji](../fin-ops-core/dev-itpro/lifecycle-services/report-production-outage.md). 

 ## <a name="see-also"></a>Informacje dodatkowe

 [Przygotowywanie do rozpoczęcia eksploatacji](hr-admin-go-live-prepare.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]