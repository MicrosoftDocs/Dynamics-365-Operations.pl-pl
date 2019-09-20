---
title: Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (20 marca 2019 r.)
description: W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 03/20/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-03-20
ms.dyn365.ops.version: Talent
ms.openlocfilehash: d316aff83bd9f60f054a970e223777db5e214adb
ms.sourcegitcommit: 45f8cea6ac75bd2f4187380546a201c056072c59
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/12/2019
ms.locfileid: "1741643"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-march-20-2019"></a>Nowości i zmiany w rozwiązaniu Dynamics 365 for Talent (20 marca 2019 r.)

[!include [banner](includes/banner.md)]

W tym temacie opisano nowe i zmienione funkcje dostępne w rozwiązaniu Microsoft Dynamics 365 for Talent.

## <a name="changes-in-attract"></a>Zmiany w Attract

### <a name="setting-the-audience-on-activities"></a>Ustawianie odbiorców dla działań
Teraz można definiować odbiorców działań w systemie. Działania związane z procesem (takie jak przeprowadzanie rozmowy kwalifikacyjnej, planowanie, opiniowanie i EEO) można ustawić dla wszystkich, wewnętrznych lub zewnętrznych kandydatów. Niestandardowe działania, na przykład formularze Microsoft, filmy na YouTube i zawartość sieciowa można dostarczać zespołowi odpowiedzialnemu za zatrudnianie lub wszystkim, wewnętrznym, albo zewnętrznym kandydatom.  

### <a name="improve-career-site-job-discoverability-search-engine-optimization"></a>Poprawienie funkcji wyszukiwania stanowisk w witrynie kariery: optymalizacja wyszukiwarki
Ta funkcja pozwala automatom aparatu wyszukiwania identyfikowanie i indeksowanie ofert pracy w witrynie kariery Attract. Pozwala to kandydatom znajdować oferty opublikowane w witrynie kariery zawodowej Attract przy użyciu popularnych aparatów wyszukiwania.

### <a name="show-login-hint-to-candidates-who-forgot-their-credentials"></a>Pokaż wskazówki logowania kandydatom, którzy zapomnieli swoich poświadczeń
Jeśli kandydat nie pamięta poświadczeń społecznościowych użytych na etapie odpowiadania na ofertę pracy, gdy kliknął otrzymane łącze, teraz system wyświetli mu wskazówki z nazwą dostawcy i użytkownika (zamazane). Pomoże to użytkownikowi podanie prawidłowych poświadczeń w celu uzyskania dostępu do zgłoszenia przesłanego w odpowiedzi na ofertę pracy.

### <a name="help-internal-candidates-explore-internal-jobs"></a>Pomoc dla wewnętrznych kandydatów w przeglądaniu wewnętrznych ofert pracy
Został rozwiązany problem polegający na tym, że zewnętrzny kandydat mógł zobaczyć nazwisko osoby rekrutującej lub menedżera zatrudniającego na stanowisko. Teraz skład zespołu zatrudniającego jest widoczny tylko dla wewnętrznych kandydatów. Ponadto wewnętrzni kandydaci mogą łatwiej wyświetlać wewnętrzne oferty pracy i łatwiej na nie odpowiadać. Gdy kandydat klika łącze, aby wyświetlić tylko wewnętrzną ofertę pracy lub na nią odpowiedzieć, system wymusza uwierzytelnianie za pomocą poświadczeń Azure Active Directory. Wewnętrzni kandydaci mogą też kontaktować się z członkiem zespołu rekrutacyjnego, aby zgłosić się do pracy na dane stanowisko lub uzyskać dodatkowe informacje. Funkcja ta jest dostępna dla wszystkich ofert pracy tylko dla wewnętrznych kandydatów. Aby uzyskać więcej informacji, zobacz [Funkcjonalność witryny rozwoju kariery w aplikacji Attract](./career-site.md).

### <a name="designate-silver-medalists-to-assign-high-value-applicants-for-future-positions"></a>Wyznaczanie srebrnych medalistów w celu przypisywania bardzo wartościowych kandydatów do przyszłych stanowisk.
Osoby prowadzące rekrutację i menedżerowie często używają list kandydatów pasujących na dane stanowisko, ale stanowisko zostało już obsadzone. Tacy kandydaci, nazywani srebrnymi medalistami, są cenni, ponieważ można się do nich zgłosić w przyszłości, gdy konieczne będzie zatrudnienie kogoś na podobnym stanowisku, oszczędzając w ten sposób czas na poszukiwania. Attract pozwala teraz osobom rekrutującym i menedżerom zatrudniającym na wskazywanie srebrnych medalistów na liście kandydatów, jeśli kandydat przejdzie do etapu oferty. Oznaczenie srebrnym medalem będzie widoczne na liście kandydatów na stanowisko oraz w widoku puli umiejętności i kandydatów, jeśli ci kandydaci widnieją w jakichkolwiek pulach danej osoby prowadzącej rekrutację lub menedżera zatrudniającego. Ponadto oznaczenie będzie widoczne w historii stanowiska jako element profilu kwalifikacji kandydata. Można uzyskać podgląd tej funkcji, o ile administrator ją włączy przy użyciu [zarządzania funkcjami w centrum administracyjnym](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature).

### <a name="add-applicants-to-talent-pools"></a>Dodawanie kandydatów do puli umiejętności i kandydatów
Teraz można łatwiej dodawać kandydatów do puli umiejętności i kandydatów za pomocą nowej akcji na liście kandydatów. Wybierając ikonę **Dodaj do puli umiejętności i kandydatów** osoba rekrutująca lub menedżer zatrudniający mogą wybierać osoby widniejące w ich puli umiejętności i kandydatów i łatwo dodawać kandydatów do puli umiejętności i kandydatów bezpośrednio z listy kandydatów na stanowisko.

### <a name="configure-whether-a-resume-is-required-to-apply-for-a-particular-job"></a>Możesz zdecydować, czy do zgłoszenia na dane stanowisko jest wymagane przesłanie życiorysu
Na podstawie opinii klientów, osoby prowadzące rekrutację mogą teraz zdecydować, czy jest konieczne przesłanie życiorysu jako załącznika do zgłoszenia kandydatury na dane stanowisko. Ta konfiguracja jest częścią działania Aplikacja dostępnego w procesie zatrudniania. Po włączeniu tej opcji każdy potencjalny kandydat zostanie poinformowany o konieczności przesłania życiorysu. Aplikacja nie będzie uznana za kompletną bez życiorysu. Pozwala to uporządkować pulę kandydatów, zapewniając, że każdy z nich dostarczył odpowiednie informacje wymagane przez zespół rekrutujący.

### <a name="candidates-can-apply-to-a-job-using-their-linkedin-profile"></a>Kandydaci mogą zgłaszać się na stanowiska za pośrednictwem swoich profili w serwisie LinkedIn
Kandydaci, którzy mają już zaktualizowane profile na LinkedIn, mogą odpowiadać na oferty pracy za pomocą jednego kliknięcia.

### <a name="track-how-a-candidate-profile-originated-in-the-system-and-where-your-applicants-discover-the-jobs-they-applied-for"></a>Można śledzić pochodzenie profilu kandydata w systemie i zobaczyć, w jaki sposób kandydat dowiedział się o ofercie pracy, na którą odpowiedział.
Teraz można ustalić skąd pochodzi profil określonego kandydata w Attract, sprawdzając źródło tego profilu w informacjach dotyczących kandydata na stronie **Profil** w aplikacji lub profilu w puli umiejętności i kandydatów. Podobnie, można sprawdzić, jak kandydat dowiedział się o ofercie pracy, sprawdzając źródło aplikacji w sekcji **działanie zgłoszenie** w źródle działania zgłoszenia. Ta informacje jest też dostępna w historii stanowiska w profilu puli umiejętności i kandydatów. Gdy osoby rekrutujące lub menedżerowie zatrudniający ręcznie dodają kandydatów, zostaną także poproszeni o podanie źródła zgłoszenia lub profilu kandydata. Jeśli kandydat zgłasza się po raz pierwszy, źródło jego profilu będzie takie samo jak pochodzenie zgłoszenia. Można uzyskać podgląd tej funkcji, o ile administrator ją włączy przy użyciu [zarządzania funkcjami w centrum administracyjnym](https://docs.microsoft.com/dynamics365/unified-operations/talent/access-preview-feature). Uwaga: w przypadku istniejących kandydatów nie będą dostępne informacje o źródle. Jednak osoby prowadzące rekrutację mogą dodać te informacje ręcznie.

## <a name="changes-in-onboard"></a>Zmiany w Onboard

Ta wersja zawiera poprawki błędów dla programu Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Zmiany w Core HR

Zmiany opisane w tej części dotyczą kompilacji 8.1.2195

### <a name="attract-integration-throws-duplicate-record-error-for-applications"></a>Integracja Attract wyświetla błąd zduplikowanych rekordów dla zgłoszeń
W tej aktualizacji problem zduplikowanych rekordów został rozwiązany. Podczas otwierania obszaru roboczego **zarządzania personelem** pojawia się błąd.

### <a name="unable-to-close-form-when-editing-name-sequence"></a>Nie można zamknąć formularza podczas edytowania kolejności nazwisk
Wprowadzono zmiany w celu naprawienia błędu występującego podczas edytowania sekwencji nazwisk w formularzu pracowników.

## <a name="coming-soon"></a>Wkrótce

###  <a name="advanced-compensation-security-fixed-and-variable"></a>Zaawansowane zabezpieczenia wynagrodzeń (stałe i zmienne)
W wielu organizacjach menedżerowie ds. wynagrodzenia i świadczeń mogą mieć dostęp tylko do konkretnych rekordów wynagrodzeń. Te rekordy mogą dotyczyć kierowników lub pracowników regionalnych. W przypadku tej zmiany można zarządzać różnymi planami wynagrodzeń dla różnych grup pracowników w organizacji. Stałe i zmienne plany mogą mieć przypisane role zabezpieczeń, które będą określały dostęp do planów i danych pracowników związanych z planami, takich jak rekordy płac i premii. Tylko role z przyznanym dostępem mogą przetwarzać wynagrodzenia tych pracowników.

###  <a name="email-support-for-alerts"></a>Pomoc techniczna e-mail dla alertów
Aktualizacja platformy 24 pozwala użytkownikom tworzyć reguły alertów, które automatycznie wysyłają powiadomienia do kontaktów w wyniku wyzwolenia przez zdarzenie.

### <a name="duplicate-employee-check-interface-changes"></a>Sprawdzanie zduplikowanych pracowników: zmiany w interfejsie
Ta zmiana powoduje, że zduplikowane pozycje są wykrywane po wypełnieniu pól nazwisk, a stan pokazuje liczbę zduplikowanych pozycji. Można wybrać podane łącze, aby otworzyć nową stronę w celu dokonania oceny, czy ma być używane wykryte dopasowanie. Aby uniknąć zakłóceń we wprowadzaniu danych, formularz zduplikowanych pozycji nie jest automatycznie otwierany.


