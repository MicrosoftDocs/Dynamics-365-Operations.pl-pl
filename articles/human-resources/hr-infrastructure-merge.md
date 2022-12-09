---
title: Scalanie infrastruktury Dynamics 365 Human Resources — omówienie
description: W tym artykule opisano scalenie infrastruktury Microsoft Dynamics 365 Human Resources.
author: twheeloc
ms.date: 10/24/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2020-10-13
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e68b28bfde35b51605aa0b653265da6261b69a90
ms.sourcegitcommit: 68efa7b89273d04484566cbe14d3533a8fd4ee53
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/02/2022
ms.locfileid: "9819250"
---
# <a name="dynamics-365-human-resources-infrastructure-merge"></a>Scalanie infrastruktury Dynamics 365 Human Resources 

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]
[!include [preview banner](../includes/preview-banner.md)]

## <a name="dynamics-human-resources-365"></a>Dynamics Human Resources 365

Microsoft Dynamics 365 Human Resources zapewnia narzędzia, które pomagają zespołom HR zwiększyć sprawność organizacyjną, przekształcić doświadczenia pracowników i zoptymalizować programy HR, aby stworzyć miejsce pracy, w którym ludzie i firma mogą się rozwijać. Aby dowiedzieć się więcej o Dynamics 365 Human Resources, zobacz [Dynamics 365 Human Resources](https://dynamics.microsoft.com/human-resources/overview/).

- **Przekształć doświadczenie pracowników.** Zatrzymaj najlepszych pracowników, umożliwiając menedżerom i pracownikom korzystanie z samoobsługowych rozwiązań, które zwiększają zaangażowanie i rozwój.
- **Optymalizacja programów HR.** Pomóż zmniejszyć koszty operacyjne i stwórz zorientowane na ludzi programy zarządzania urlopami i nieobecnościami, czasem, świadczeniami i wynagrodzeniami.
- **Zwiększanie sprawności organizacyjnej.** Umożliwić HR działanie ze sprawnością, jakiej wymaga biznes, wykorzystując Dataverse i Microsoft Power Platform do centralizacji danych o ludziach i łatwego rozszerzania Dynamics 365 Human Resources.
- **Odkryj wiedzę o pracownikach.** Podejmuj decyzje na podstawie danych, dzięki możliwości analizowania i wizualizacji danych o ludziach na bogatych pulpitach, dostępnych na każdym urządzeniu.

## <a name="human-resources-infrastructure-merge"></a>Scalanie infrastruktury rozwiązania Human Resources

Dynamics 365 Human Resources jest samodzielną aplikacją, która obecnie korzysta z innej infrastruktury niż pozostałe aplikacje finansowe i operacyjne, takie jak Dynamics 365 Finance lub Dynamics 365 Supply Chain Management. Scalanie infrastruktury przeniesie Dynamics 365 Human Resources do tej samej infrastruktury, co inne aplikacje finansowe i operacyjne.

Aby dowiedzieć się więcej o łączeniu infrastruktury Human Resources, zobacz [Scalanie ofert HR](https://cloudblogs.microsoft.com/dynamics365/it/2021/09/15/merging-of-hr-offerings-brings-capabilities-together-for-customers/). Aby uzyskać odpowiedzi na często zadawane pytania, zobacz [Często zadawane pytania dotyczące scalania infrastruktury rozwiązania Human Resources](./hr-infrastructure-merge-faq.md).

## <a name="customer-migration-vs-customer-merge"></a>Migracja odbiorcy a scalenie odbiorcy

Jako część scalania infrastruktury, wszystkie możliwości aplikacji Human Resources zostały udostępnione w środowiskach finansowych i operacyjnych. Klienci mogą migrować swoje środowiska Human Resources za pomocą narzędzia migracji dostępnego w usługach Microsoft Dynamics Lifecycle Services. Mogą również opcjonalnie scalić dane z istniejącym środowiskiem finansów i operacji. 

Migracja odbiorcy i scalanie odbiorcy różnią się następująco:

- **Migracja klientów** — automatyczne narzędzie migracji jest używane do przeprowadzania migracji metodą „lift-and-shift” (przesunięcia) bazy danych klientów z infrastruktury Human Resources do infrastruktury finansów i operacji. W wyniku tego jest nowe środowisko finansowe i operacyjne, w którym jest używana baza danych Human Resources odbiorcy. 
- **Scalanie odbiorcy** — ten dodatkowy krok nie jest wymagany przez firmę Microsoft. Jest to wykonywane według uznaniowości odbiorcy i według własnej osi czasu odbiorcy. W trakcie tego kroku dane klienta są przenoszone do istniejącego środowiska, takiego jak Finance lub Project Operations. Ten element jest w większości ręczny i można go wykonać przy użyciu jednostek danych DMF (Data Management Framework). 

## <a name="planning-a-human-resources-environment-migration"></a>Planowanie migrowania środowiska Human Resources

W ramach scalania infrastruktury wszyscy odbiorcy będą potrzebni do migrowania istniejącego środowiska Human Resources z autonomicznej infrastruktury. Aby pomóc w tym procesie, zaleca się korzystanie ze zautomatyzowanego narzędzia migracji w usługach Lifecycle Services, aby przenieść bieżące środowiska do nowej infrastruktury. 

Poniższe sekcje zawierają więcej szczegółów dotyczących używania narzędzi usługi Lifecycle Services do migrowania autonomicznego środowiska Human Resources. 

Odbiorcy, którzy planują migrację, mogą mieć następujące oczekiwania:

- Wszyscy klienci będą musieli przeprowadzić migrację do środowiska piaskownicy przed migracją środowiska produkcyjnego. 
- Narzędzie migracji umożliwia tylko migrację piaskownicy do piaskownicy i migrację produkcji do produkcji. W związku z tym typ środowiska określa, które środowisko można odpowiednio przenieść. 
- Klienci mogą migrować tyle piaskownic, ile to konieczne, przed migracją środowiska produkcyjnego, pod warunkiem, że jest dostępne docelowe gniazdo piaskownicy. Klienci mogą także wielokrotnie usunąć zmigrowaną piaskownicę i dokonać jej ponownej migracji. 
- Jeśli migracja piaskownicy nie powiedzie się lub będzie trzeba rozpocząć ją od początku, możesz usunąć środowisko z infrastruktury finansów i operacji i ponownie zmigrować to samo środowisko.
- Adres URL środowiska Human Resources będzie się różnić po zakończeniu migracji.
- Zaplanuj odpowiednią ilość przestoju dla swojej firmy podczas migracji środowiska produkcyjnego. Szacowany okres ukończenia automatycznego procesu migracji wynosi trzy do czterech godzin. Okres czasu zmienia się w zależności od danych organizacji. Należy sprawdzić ilość czasu wymaganego podczas migracji środowiska piaskownicy i zezwolić na wykonywanie wszelkich dodatkowych zadań ręcznych.

> [!IMPORTANT] 
> Po pomyślnym zmigrowanie środowiska produkcyjnego do infrastruktury finansów i operacji źródło autonomicznego środowiska produkcyjnego jest automatycznie usuwane. Nie należy usuwać zmigrowanego środowiska produkcyjnego. 

Proces migracji odbywa się w większości automatycznie. Jednak po zakończeniu migracji użytkownicy biznesowi muszą wykonać kilka ręcznych kroków i weryfikacji.

Należy wykonać ręcznie następujące kroki:

- Utwórz nowy projekt usługi Lifecycle Services dla migracji.
- Sprawdź wszystkie integracje w starym środowisku do nowego środowiska, wskazując integrację do nowego adresu URL/punktów końcowych opartych na każdej konfiguracji integracji.
- Odśwież magazyn danych dla raportów osadzonych Power BI.
- Odśwież listę jednostek danych z obszaru roboczego DMF.
- Łącze do usługi Lifecycle Services w celu pomocy.
- Tworzenie kalendarzy obrachunkowych.

W procesie automatycznym następujące akcje zostały zakończone i muszą zostać sprawdzone:

- Dane:

    - Konfiguracje
    - Role zabezpieczeń (w tym role niestandardowe)
    - Przepływy pracy (w tym powiadomienia)
    - Personalizacja i zapisane widoki
    - Transakcje
    - Pola niestandardowe
    - Załączniki
    - Alerty

- Zarządzanie danymi — używanie własnej bazy danych (BYOD)
- Zarządzanie funkcjami — włączone/wyłączone funkcje.
- Osadzona usługa Power Apps.
- Dołączone środowisko centrum administracyjnego Power Platform (tylko produkcja).
- Zadania wsadowe.
- Dla każdej osoby prawnej jest tworzona pusta księga. Domyślny typ wymiany walut i waluta rozliczeniowa są ustawiane dla każdej księgi.
- Nowy plan kont jest automatycznie tworzony i łączony ze stroną **Księga** w każdej osobie prawnej. Wymiary finansowe skonfigurowane w środowisku Human Resources zostaną automatycznie dodane do nowej struktury konta i połączone z księgą. 

> [!NOTE]
> Księga jest wymagana dla infrastruktury finansowej i operacyjnej jako część produktu Dynamics 365 Finance. Kontroler wymiarów niestandardowych, który istniał w aplikacji autonomicznej Dynamics 365 Human Resources, nie jest niedostępny. Scalona infrastruktura modułu Human Resources zależy od logiki rozwiązania Finance, aby wyświetlić wymiary finansowe w module **Human Resources**. Aby uzyskać więcej informacji o wymiarach planu kont i wymiarach finansowych, zobacz [tutaj](../finance/general-ledger/plan-chart-of-accounts.md). 

## <a name="considerations"></a>Uwarunkowania

- Migracja do środowisk będzie zawsze dostępna w najnowszej ogólnie dostępnej wersji (GA). W zależności od migracji i planu testowania, jeśli weryfikacja migracji dla środowisk piaskownicy miała inną wersję, zalecane jest zweryfikowanie migracji piaskownicy w tej samej wersji co środowisko produkcyjne. 
- Podczas migracji zmigrowane środowiska zostaną umieszczone w tym samym regionie co autonomiczne źródłowe środowiska Human Resources.

## <a name="licensing"></a>Licencjonowanie

W poniższych obszarach nie ma żadnych zmian w licencji Dynamics 365 Human Resources: 

- **Minimalna liczba wymagań zakupu licencji**
- **Licencje na środowisko produkcyjne i środowisko piaskownicy** — jeśli są dostępne autonomiczne licencje Human Resources, które zawierają jedno środowisko produkcyjne i jedno środowisko piaskownicy, w infrastrukturach finansowych i operacyjnych jest dostępna taka sama liczba licencji bez dodatkowych opłat.
- **Dodatkowe licencje na piaskownicę** — jeśli zakupiono dodatkowe licencje na piaskownicę dla autonomicznej aplikacji Human Resources, ta sama liczba licencji piaskownicy będzie dostępna dla standardowego środowiska testowego akceptacji (piaskownica) w infrastrukturach finansowych i operacyjnych bez dodatkowych opłat. 
