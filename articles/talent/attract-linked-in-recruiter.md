---
title: Korzystanie z aplikacji LinkedIn Recruiter
description: "Ten temat zawiera informacje o używaniu funkcji uczenia maszynowego do generowania rekomendacji funkcji i kandydatów na funkcje."
author: josaw
manager: AnnBe
ms.date: 12/07/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-talent
ms.technology: 
ms.search.form: 
audience: Application User
ms.reviewer: josaw
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: 
ms.author: josaw
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.translationtype: HT
ms.sourcegitcommit: be66d9f95551066bb8bc25445c652d4fa59066d4
ms.openlocfilehash: 9bb323728923ff3b09ff0bfba3849f3c5d84eb34
ms.contentlocale: pl-pl
ms.lasthandoff: 12/07/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a>Korzystanie z aplikacji LinkedIn Recruiter
[!include[banner](../includes/banner.md)]

LinkedIn to największa na świecie baza danych pracowników i osób szukających pracy oraz często główny system, którego osoby rekrutujące używają do wyszukiwania, komunikowania się i pozyskiwania kandydatów na funkcje, które chcą obsadzić. Integracja aplikacji LinkedIn Recruiter z aplikacją Dynamics 365 for Talent Attract ułatwia użytkownikom zatrudnianie osób oraz synchronizowanie danych między oboma systemami.

> [!NOTE]
> Aby można było korzystać z integracji aplikacji LinkedIn Recruiter z aplikacją Attract, trzeba mieć dodatek kompleksowej obsługi rekrutacji oraz wykupione stanowiska w aplikacji LinkedIn Recruiter.

## <a name="set-up-linkedin-recruiter-with-attract"></a>Konfigurowanie współdziałania aplikacji LinkedIn Recruiter z aplikacją Attract 

Zanim będzie można używać funkcji aplikacji LinkedIn Recruiter, należy skonfigurować dostęp na poziomie umowy lub firmy w wystąpieniu aplikacji Attract. W celu przeprowadzenia procesu konfiguracji należy współpracować z użytkownikiem, który jest administratorem umowy na usługę LinkedIn Recruiter. Aby skonfigurować współdziałanie aplikacji LinkedIn Recruiter i Attract, wykonaj poniższe kroki.

1.  Zaloguj się w aplikacji Attract jako administrator i przejdź do okna **Ustawienia administratora**.

2.  W lewym okienku kliknij kartę **Integracja z serwisem LinkedIn**.

[![Widok administratora aplikacji Attract przy rozpoczynaniu integracji z aplikacją LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)

3.  Kliknij przycisk **Połącz**, aby uruchomić instalatora i zostać przeprowadzonym przez proces logowania do serwisu LinkedIn.

4.  Jeśli masz stanowiska w różnych umowach na LinkedIn, zaznacz umowę, którą chcesz połączyć z systemem Attract. Jeśli masz stanowisko tylko w jednej umowie na LinkedIn, ten krok nie będzie potrzebny.

5.  Widżet serwisu LinkedIn załaduje teraz Twoje ustawienia administratora z wyświetloną listą integracji. W obszarze **Połącz z systemem Recruiter** kliknij przycisk **Poproś**.

[![Widok administratora aplikacji Attract przy wnioskowaniu o integrację z aplikacją LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)

6.  Po wysłaniu prośby o integrację z aplikacji Attract aplikacja będzie wyświetlana jako **Gotowa do współpracy** i można ją włączyć z okna **Ustawienia administratora aplikacji Recruiter**. Jeśli na tej stronie zobaczysz przycisk **Powiadom partnera**, poczekaj kilka sekund, kliknij przycisk **Powiadom partnera**, a następnie odśwież stronę. Napis powinien się zmienić na **Gotowa do współpracy**.

[![Widok administratora aplikacji Attract wskazujący, że wszystkie żądania po stronie aplikacji Attract zostały wykonane](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)

Aby wykonać następny krok, musisz mieć uprawnienia administratora w umowie na usługę LinkedIn Recruiter.

7.  Zaloguj się w serwisie LinkedIn przy użyciu konta administratora i przejdź do aplikacji LinkedIn Recruiter, klikając opcję w prawym górnym rogu. 

8. W menu **More** (Więcej) w górnej części ekranu kliknij przycisk **Admin Settings** (Ustawienia administratora), a następnie kliknij kartę **ATS**.

System Attract będzie wyświetlony z kilkoma opcjami, które można włączyć.

9. Jeśli chcesz włączyć tylko funkcję eksportu jednym kliknięciem dla **wskaźnika danych z systemu ATS** i **widżetu profilu danych z systemu ATS**, wybierz opcję **Company-level access** (Dostęp na poziomie firmy). Aby włączyć wszystkie funkcje dostępu na poziomie firmy oraz dostęp do historii wiadomości InMail, historii notatek i profilu szczątkowego InMail, wybierz opcję **Contract-level access** (Dostęp na poziomie umowy).

10. Włącz żądany poziom dostępu w ustawieniach **administratora systemu ATS** w aplikacji LinkedIn Recruiter.

[![Włączanie integracji z aplikacją Attract z widoku administratora aplikacji LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)

12. Wróć do okna ustawień administratora aplikacji Attract jako administrator aplikacji Attract i kliknij kartę **Integracja z serwisem LinkedIn**. Powinien być teraz widoczny załadowany widżet serwisu LinkedIn z podpisem **Włączone** oraz włączonym wybranym poziomem dostępu.

[![Integracja z aplikacją LinkedIn Recruiter zakończona](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)

## <a name="using-linkedin-recruiter-capabilities"></a>Używanie funkcji aplikacji LinkedIn Recruiter

Gdy administrator aplikacji Attract włączy funkcje aplikacji LinkedIn Recruiter, będą one dostępne dla menedżerów zatrudniających i osób rekrutujących. Aby korzystać z tych funkcji, podłącz konto serwisu LinkedIn w obszarze **Ustawienia użytkownika**. Połączenie ustawień administratora i użytkownika spowoduje udostępnienie kilku funkcji.

### <a name="in-ats-profile-widget"></a>Widżet profilu danych z systemu ATS

W aplikacji Attract można wyświetlić profil kandydata z serwisu LinkedIn. Widżet serwisu LinkedIn będzie pokazywał profil kandydata, jeśli informacje w systemie ATS pasują do danych użytkownika w serwisie LinkedIn.

Aby wyświetlić profil kandydata, przejdź do niego z poziomu stanowiska lub puli umiejętności. W profilu kandydata kliknij kartę **LinkedIn**, a widżet profilu zostanie załadowany. Z tej strony można również zapisać kandydata do projektów w usłudze LinkedIn Recruiter.
1. Jeśli LinkedIn znalazł (dokładne) dopasowanie na podstawie adresu e-mail i identyfikatora elementu członkowskiego LinkedIn, wyświetlany jest profil kandydata. Użytkownik nadal może połączyć/rozłączyć profil.

2. Jeśli LinkedIn nie może znaleźć kandydata na podstawie jego adresu e-mail lub identyfikatora członka, wyświetli listę możliwych dopasowań kandydatów na podstawie nazwy kandydata i użytkownik może wybrać jednego z nich i połączyć profil.  

3. Jeśli LinkedIn nie może znaleźć żadnego kandydata na podstawie nazwy, zwróci informację, że nie znaleziono dopasowania.

### <a name="1-click-export"></a>Eksport jednym kliknięciem 

W trakcie pozyskiwania kandydatów z serwisu LinkedIn można jednym kliknięciem wyeksportować kandydata do aktualnie otwartych funkcji. Aby skonfigurować funkcję eksportu jednym kliknięciem, wykonaj kroki opisane poniżej. Przed wykonaniem tych czynności upewnij się, że masz przypisaną rolę Menedżer zatrudniający lub Osoba rekrutująca wobec funkcji, a funkcja jest na etapie **Prospekt**.

1.  Utwórz funkcję, przypisz odpowiednie role i aktywuj funkcję.

2.  Po uaktywnieniu funkcji przejdź do aplikacji LinkedIn Recruiter.

3.  Odszukaj żądanego kandydata i przejdź do jego profilu.

4.  Używając pola wyszukiwania funkcji na karcie kontaktu, znajdź funkcję na podstawie tytułu lub identyfikatora funkcji aktywowanego w aplikacji Attract. Jeśli nie można znaleźć funkcji, kliknij przycisk **Change ATS** (Zmień system ATS) i poszukaj prawidłowego wystąpienia aplikacji Attract.

5. Po wybraniu funkcji kliknij przycisk **Export** (Eksportuj). Kandydat został teraz pobrany przez aplikację Attract.

6.  Przejdź do aplikacji Attract i otwórz odnośną funkcję. Wyeksportowany kandydat będzie widoczny w funkcji na etapie **Prospekt**.

### <a name="in-ats-indicator"></a>Wskaźnik danych z systemu ATS 

W aplikacji LinkedIn Recruiter można śledzić, czy kandydat aplikował na inne funkcje w Twojej organizacji, sprawdzić, na których etapach ubiegania się o pracę jest obecnie, oraz obejrzeć informacje zwrotne i komentarze z aplikacji Attract.

1.  Otwórz aplikację LinkedIn Recruiter i znajdź profil żądanego kandydata.

2.  Przewiń profil kandydata w dół do sekcji **In-ATS** (Dane z systemu ATS).

3.  Za pomocą tego widżetu można w widoku aplikacji LinkedIn Recruiter wyświetlić wszystkie informacje o kandydacie, które znajdują się w aplikacji Attract.

4.  Kliknij kartę **Jobs & Statuses** (Funkcje i statusy), aby wyświetlić funkcje zajmowane przez kandydata, jego najnowszy status oraz zachowanie na poszczególnych funkcjach.

5.  Na karcie **Interview Feedback** (Opinie po rozmowach kwalifikacyjnych) widać opinie przesłane przez osoby prowadzące rozmowy kwalifikacyjne do aplikacji Attract.

6.  Na karcie **Notes** (Uwagi) widać notatki sporządzone o tym kandydacie w aplikacji Attract.

> [!NOTE]
> Dane kandydata i aplikacji nie będą synchronizowane z usługą LinkedIn Recruiter, jeśli kandydat nie wyszedł poza etap prospektu.

### <a name="inmail-history"></a>Historia wiadomości InMail

Historia wiadomości InMail w serwisie LinkedIn jest aktywna przy dostępie na poziomie umowy do usługi LinkedIn Recruiter. Po włączeniu tej opcji można przeglądać całą historię wiadomości InMail wymienianych z kandydatem. Można także sprawdzić, kto jeszcze z organizacji komunikował się z kandydatem za pomocą wiadomości InMail, jednak nie można wyświetlić treści tych wiadomości.

Aby wyświetlić historię wiadomości InMail, przejdź do profilu kandydata, przejdź do karty **LinkedIn** i przewiń do dołu strony. W przypadku rozmowy z kandydatami można przejrzeć historię InMail. Wiadomości InMail będą synchronizowane z aplikacją Attract co kilka godzin.

### <a name="notes-history"></a>Historia notatek 

Historia notatek w serwisie LinkedIn jest aktywna przy dostępie na poziomie umowy do usługi LinkedIn Recruiter. Po włączeniu tej opcji można wyświetlać notatki sporządzone o kandydacie przez różne osoby rekrutujące z Twojej organizacji.

Aby wyświetlić historię notatek, przejdź do profilu kandydata, przejdź do karty **LinkedIn** i przewiń do dołu strony. W aplikacji LinkedIn Recruiter można przeglądać wszystkie notatki o kandydacie.

### <a name="inmail-stub-profile"></a>Profil szczątkowy InMail

Profil szczątkowy InMail jest aktywny przy dostępie na poziomie umowy do usługi LinkedIn Recruiter. Jeśli kandydaci zgodzą się udostępnić swoje profile z serwisu LinkedIn któremukolwiek użytkownikowi w Twojej organizacji, możesz śledzić tych kandydatów w aplikacji Attract, a dla każdego kandydata zostanie utworzony nowy rekord kandydata. Jeśli kandydat już istnieje w systemie z adresem e-mail lub zdecydował się udostępnić swój adres rekruterowi, można wyświetlić adres e-mail kandydata.

Aby wyświetlić listę kandydatów, przejdź do okna **Pule umiejętności**, a zobaczysz listę pul umiejętności utworzoną w usłudze LinkedIn przez system. Ta pula umiejętności zawiera listę kandydatów i ich profile szczątkowe otrzymane z serwisu LinkedIn, tylko z imionami i nazwiskami kandydatów. Identyfikator e-mail kandydata będzie widoczny tylko wtedy, gdy udostępnił on swój adres e-mail.

