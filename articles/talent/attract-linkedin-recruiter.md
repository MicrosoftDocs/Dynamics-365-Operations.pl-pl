---
title: Pozyskiwanie kandydatów za pomocą LinkedIn Recruiter w aplikacji Attract
description: Skorzystaj z integracji serwisu LinkedIn dostarczonej przez firmę Microsoft Dynamics 365 Talent - Attract, aby znajdować kandydatów przez LinkedIn Recruiter.
author: andreabichsel
manager: AnnBe
ms.date: 08/31/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent, Core
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.search.industry: ''
ms.author: anbichse
ms.search.validFrom: 2018-10-15
ms.dyn365.ops.version: Talent October 2018 update
ms.openlocfilehash: 96e4660c4958bf5f2a0910bfad770e1e713f800f
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/17/2020
ms.locfileid: "4528276"
---
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a>Pozyskiwanie kandydatów za pomocą LinkedIn Recruiter w aplikacji Attract

[!include [banner](includes/banner.md)]

LinkedIn to największa na świecie sieć profesjonalistów w trybie online, która daje dostęp do talentów na świecie. Microsoft Dynamics 365 Talent: Attract pozwala na pozyskiwanie kandydatów bezpośrednio z serwisu LinkedIn. Dzięki temu łatwiej niż kiedykolwiek można znaleźć talent, który wypełni otwarte stanowisko. Po skonfigurowaniu połączenia z usługą LinkedIn za pomocą Attract można przejrzeć potencjalnych kandydatów serwisu LinkedIn w odniesieniu do stanowisk i wyeksportować ich do Attract za pomocą jednego kliknięcia.

Jeśli nie masz takiej możliwości, skontaktuj się z administratorem. Aby można było skorzystać z LinkedIn Recruiter za pomocą Attract, administrator musi [skonfigurować integrację z serwisem LinkedIn](./attract-admin-linkedin.md). Następnie można skonfigurować połączenie LinkedIn Recruiter i rozpocząć wyszukiwanie kandydatów.

>[!IMPORTANT]
>Z dniem 1 lipca 2020 serwis LinkedIn nie obsługuje już Internet Explorer 11. Użytkownicy mogą nadal uzyskiwać dostęp do serwisu LinkedIn za pomocą Internet Explorer 11, ale będą monitowani o uaktualnienie lub użycie innej przeglądarki. Aby uzyskać więcej informacji, zajrzyj [do obsługiwanych przeglądarek internetowych dla serwisu LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).

## <a name="set-up-your-connection-with-linkedin-recruiter"></a>Skonfiguruj połączenie za pomocą systemu LinkedIn Recruiter

Aby można było rozpocząć pracę LinkedIn Recruiter za pomocą Attract, należy skonfigurować połączenie z LinkedIn Recruiter. W tym kroku są potrzebne poświadczenia użytkownika LinkedIn Recruiter.

1. Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu strony.
2. Wubierz **Ustawienia użytkownika**.
3. Na karcie **Połączenia** wybierz opcję **Połącz** obok pozycji **LinkedIn**. Postępuj zgodnie z instrukcjami dostarczonymi przez serwis LinkedIn.

    ![[Ustawianie połączenia z przyciąganiem do LinkedIn Recruiter](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a>Wyświetlanie kandydatów LinkedIn w Attract

Po nawiązaniu połączenia z LinkedIn Recruiter można wyświetlić Profile kandydatów w serwisie LinkedIn w Attract.

>[!NOTE]
>Jeśli masz przypisane stanowisko rekrutacji, możesz zobaczyć pełne informacje dotyczące kandydatów.<br><br>
>Jeśli masz stanowisko Menedżera zatrudnienia lub nie masz przypisanego stanowiska, Wyloguj się z serwisu LinkedIn lub LinkedIn Recruiter przed przejściem do karty LinkedIn w celu przyciągania kandydata. Użytkownik będzie mógł zobaczyć podstawowe dane profilu publicznego kandydata, takie jak imię i nazwisko.

1. W Attract celu wybierz **Prace** lub **Pule talentów** po lewej stronie, a następnie wybierz kandydata.

    ![[Wyświetlanie kandydatów LinkedIn w Attract](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. W profilu kandydata wybierz kartę **LinkedIn**. Można wyświetlić profil kandydata z historią InMail.

   ![Wyświetl informacje dotyczące kandydata w serwisie LinkedIn](./media/attract-candidate-linkedin-tab.png)

W tym oknie można wykonać następujące czynności:

- Wybierz **kartę działania rekrutacji**, aby wyświetlić:
   
   - Notatki dotyczące rekrutacji (publiczne i prywatne). Domyślnie notatki są prywatne i widoczne tylko dla właściciela notatek.
   - Aktywność InMail (ale nie zawartość InMail). Przewiń do dołu strony, aby wyświetlić InMail wymianę informacji z kandydatem i wyświetlić innych użytkowników w organizacji, którzy komunikują się z kandydatem.
   - Działanie związane z odrzuceniem kandydata

- Wybierz przycisk **Wyślij InMail**, aby wysłać wiadomość InMail bez konieczności opuszczania Attract.

- Wybierz opcję **Zapisz do zadania**, aby zapisać zadanie bez opuszczania Attract.

> [!NOTE]
> Profil LinkedIn kandydata zostanie wyświetlony w Attract, gdy informacje Attract kandydata będą zgodne z danymi LinkedIn. Oto stosowane reguły dopasowywania:
> 
> 1. Jeśli adres e-mail i identyfikator członka serwisu LinkedIn zgadzają się w Attract i LinkedIn, wyświetlany jest profil kandydata. Kandydaci nadal mają możliwość łączenia lub odłączania profilu LinkedIn w Attract.
> 2. Jeśli adres e-mail lub identyfikator członka LinkedIn nie zgadza się, zostanie wyświetlona lista możliwych kandydatów. Następnie można wybrać kandydata z listy i połączyć profil.
> 3. Jeśli nie ma żadnych dobrych odpowiedników, zostanie wyświetlone powiadomienie, że nie znaleziono odpowiednika.

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a>Eksportowanie kandydatów LinkedIn do Attract za pomocą jednego kliknięcia

Podczas przeglądania kandydatów w LinkedIn Recruiter można eksportować ich do aktualnie otwartych stanowisk w Attract. W tym kroku przyciąganie wymaga uprawnień Rekrutacja lub Menedżer zatrudniania w Attract. Aby uzyskać więcej informacji o rolach w Attract, zobacz [Zarządzanie zabezpieczeniami i rolami w aplikacji Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).

Należy również upewnić się, że zadanie ma etap prospektu. Aby uzyskać więcej informacji, zobacz [Działanie Prospekt](./activities-attract.md#prospect-activity).

1. W Attract utwórz funkcję, przypisz odpowiednie role i aktywuj pracę.
2. W LinkedIn Recruiter znajdź dobrego kandydata do pracy i przejdź do profilu kandydata.
3. Używając pola wyszukiwania pracy na karcie kontaktu, znajdź pracę na podstawie tytułu lub identyfikatora pracy aktywowanego w aplikacji Attract. Jeśli nie można znaleźć pracy, kliknij przycisk **Change ATS** (Zmień system ATS) i poszukaj prawidłowego wystąpienia aplikacji Attract.
4. Wybierz stanowisko i kliknij przycisk **Eksportuj**.
5. Otwórz pracę w Attract. Wyeksportowany kandydat zostanie wyświetlony na karcie pracy **Prospekt**.

## <a name="view-attract-information-in-linkedin-recruiter"></a>Wyświetl informacje o Attract w LinkedIn Recruiter

W aplikacji LinkedIn Recruiter można śledzić, czy kandydat aplikował na inne stanowiska w Twojej organizacji, sprawdzić, na których etapach ubiegania się o pracę jest obecnie, oraz obejrzeć informacje zwrotne i komentarze z aplikacji Attract.

1. Otwórz LinkedIn Recruiter i wybierz profil kandydata.
2. Umieść wskaźnik myszy na **W ATS**.
3. Wybierz jedną z następujących opcji, aby wyświetlić informacje o kandydatach, które są przechowywane w Attract:

    - **Prace i statusy** — wyświetlanie stanowisk, których częścią jest kandydat, najnowszego statusu i sposobu, etap procesu kandydata dla każdego stanowiska.
    - **Opinie po rozmowach kwalifikacyjnych** – wyświetla opinie przesłane przez osoby prowadzące rozmowy kwalifikacyjne do aplikacji Attract.
    - **Notatki** — zajrzyj do notatek wprowadzonych dla tego kandydata w Attract.

    ![[Wyświetl informacje Attract z LinkedIn Recruiter](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> Dane kandydata i aplikacji nie będą synchronizowane z usługą LinkedIn Recruiter, jeśli kandydat nie wyszedł poza etap Prospektu.

## <a name="view-linkedin-talent-pools"></a>Wyświetlanie pul talentów w serwisie LinkedIn

Jeśli kandydaci zgadzają się na udostępnianie swoich profilów LinkedIn innym użytkownikom w organizacji, zostanie utworzony nowy rekord kandydata w Attract. Następnie te kandydaci znajdują się w puli talentów w systemie tworzonym w serwisie LinkedIn.

1. W Attract należy wybrać **pulę talentów** po lewej stronie.
2. Wybierz pulę talentów serwisu LinkedIn. Zostanie wyświetlona lista kandydatów i ich profili szczątkowych z serwisu LinkedIn. Profile szczątkowe zawierają imiona i nazwiska i adresy e-mail kandydata, jeśli kandydat pobrał opcję jego udostępnienia.

## <a name="see-also"></a>Informacje dodatkowe

[Konfigurowanie integracji Attract z serwisem LinkedIn — często zadawane pytania](./attract-linkedin-faq.md)

[Konfigurowanie integracji z serwisem LinkedIn dla aplikacji Microsoft Dynamics 365 Talent - Attract](./attract-admin-linkedin.md)

[Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract](./creating-jobs-attract.md)

[Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Microsoft Dynamics 365 Talent - Attract](./attract-post-jobs-to-linkedin.md)

[Rozwiązywanie problemów z integracją usługi LinkedIn i Microsoft Dynamics 365 Talent - Attract](./attract-troubleshoot-linkedin.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]