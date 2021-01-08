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
# <a name="source-candidates-with-linkedin-recruiter-in-attract"></a><span data-ttu-id="e4da4-103">Pozyskiwanie kandydatów za pomocą LinkedIn Recruiter w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-103">Source candidates with LinkedIn Recruiter in Attract</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="e4da4-104">LinkedIn to największa na świecie sieć profesjonalistów w trybie online, która daje dostęp do talentów na świecie.</span><span class="sxs-lookup"><span data-stu-id="e4da4-104">LinkedIn is the world's largest online professional network, giving you access to the world's top talent.</span></span> <span data-ttu-id="e4da4-105">Microsoft Dynamics 365 Talent: Attract pozwala na pozyskiwanie kandydatów bezpośrednio z serwisu LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e4da4-105">Microsoft Dynamics 365 Talent: Attract lets you source candidates directly from LinkedIn.</span></span> <span data-ttu-id="e4da4-106">Dzięki temu łatwiej niż kiedykolwiek można znaleźć talent, który wypełni otwarte stanowisko.</span><span class="sxs-lookup"><span data-stu-id="e4da4-106">Therefore, it's easier than ever to find the talent that you need to fill your open positions.</span></span> <span data-ttu-id="e4da4-107">Po skonfigurowaniu połączenia z usługą LinkedIn za pomocą Attract można przejrzeć potencjalnych kandydatów serwisu LinkedIn w odniesieniu do stanowisk i wyeksportować ich do Attract za pomocą jednego kliknięcia.</span><span class="sxs-lookup"><span data-stu-id="e4da4-107">After you set up your connection with LinkedIn through Attract, you can view potential LinkedIn candidates for your positions and export them into Attract with just one click.</span></span>

<span data-ttu-id="e4da4-108">Jeśli nie masz takiej możliwości, skontaktuj się z administratorem. Aby można było skorzystać z LinkedIn Recruiter za pomocą Attract, administrator musi [skonfigurować integrację z serwisem LinkedIn](./attract-admin-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="e4da4-108">If you don't seem to have this capability, contact your admin. Before you can take advantage of LinkedIn Recruiter from Attract, your admin must [set up integration with LinkedIn](./attract-admin-linkedin.md).</span></span> <span data-ttu-id="e4da4-109">Następnie można skonfigurować połączenie LinkedIn Recruiter i rozpocząć wyszukiwanie kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e4da4-109">You can then set up your connection with LinkedIn Recruiter and start finding candidates.</span></span>

>[!IMPORTANT]
><span data-ttu-id="e4da4-110">Z dniem 1 lipca 2020 serwis LinkedIn nie obsługuje już Internet Explorer 11.</span><span class="sxs-lookup"><span data-stu-id="e4da4-110">As of July 1, 2020, LinkedIn no longer supports Internet Explorer 11.</span></span> <span data-ttu-id="e4da4-111">Użytkownicy mogą nadal uzyskiwać dostęp do serwisu LinkedIn za pomocą Internet Explorer 11, ale będą monitowani o uaktualnienie lub użycie innej przeglądarki.</span><span class="sxs-lookup"><span data-stu-id="e4da4-111">Users can still access LinkedIn with Internet Explorer 11, but will be prompted to upgrade or use a different browser.</span></span> <span data-ttu-id="e4da4-112">Aby uzyskać więcej informacji, zajrzyj [do obsługiwanych przeglądarek internetowych dla serwisu LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).</span><span class="sxs-lookup"><span data-stu-id="e4da4-112">For more information, see [Supported Internet Browsers for LinkedIn](https://www.linkedin.com/help/linkedin/answer/4135/supported-internet-browsers-for-linkedin).</span></span>

## <a name="set-up-your-connection-with-linkedin-recruiter"></a><span data-ttu-id="e4da4-113">Skonfiguruj połączenie za pomocą systemu LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="e4da4-113">Set up your connection with LinkedIn Recruiter</span></span>

<span data-ttu-id="e4da4-114">Aby można było rozpocząć pracę LinkedIn Recruiter za pomocą Attract, należy skonfigurować połączenie z LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="e4da4-114">Before you can start working with LinkedIn Recruiter through Attract, you must set up your connection with LinkedIn Recruiter.</span></span> <span data-ttu-id="e4da4-115">W tym kroku są potrzebne poświadczenia użytkownika LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="e4da4-115">For this step, you need your LinkedIn Recruiter credentials.</span></span>

1. <span data-ttu-id="e4da4-116">Kliknij przycisk **Ustawienia** (symbol koła zębatego) w prawym górnym rogu strony.</span><span class="sxs-lookup"><span data-stu-id="e4da4-116">Select the **Settings** button (gear icon) in the upper-right corner of the page.</span></span>
2. <span data-ttu-id="e4da4-117">Wubierz **Ustawienia użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="e4da4-117">Select **User settings**.</span></span>
3. <span data-ttu-id="e4da4-118">Na karcie **Połączenia** wybierz opcję **Połącz** obok pozycji **LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="e4da4-118">On the **Connections** tab, select **Connect** next to **LinkedIn**.</span></span> <span data-ttu-id="e4da4-119">Postępuj zgodnie z instrukcjami dostarczonymi przez serwis LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e4da4-119">Follow the instructions that are provided by LinkedIn.</span></span>

    ![[<span data-ttu-id="e4da4-120">Ustawianie połączenia z przyciąganiem do LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="e4da4-120">Set up connection to LinkedIn Recruiter from Attract</span></span>](./media/attract-set-up-linkedin-recruiter-connection.png)](./media/attract-set-up-linkedin-recruiter-connection.png)

## <a name="view-linkedin-candidates-in-attract"></a><span data-ttu-id="e4da4-121">Wyświetlanie kandydatów LinkedIn w Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-121">View LinkedIn candidates in Attract</span></span>

<span data-ttu-id="e4da4-122">Po nawiązaniu połączenia z LinkedIn Recruiter można wyświetlić Profile kandydatów w serwisie LinkedIn w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-122">After you're connected to LinkedIn Recruiter, you can view candidates' LinkedIn profiles in Attract.</span></span>

>[!NOTE]
><span data-ttu-id="e4da4-123">Jeśli masz przypisane stanowisko rekrutacji, możesz zobaczyć pełne informacje dotyczące kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e4da4-123">If you have a Recruiter seat assigned to you, you can see the candidates' full information.</span></span><br><br>
><span data-ttu-id="e4da4-124">Jeśli masz stanowisko Menedżera zatrudnienia lub nie masz przypisanego stanowiska, Wyloguj się z serwisu LinkedIn lub LinkedIn Recruiter przed przejściem do karty LinkedIn w celu przyciągania kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4da4-124">If you have a Hiring Manager seat or no seat assigned to you, be sure to sign out of LinkedIn or LinkedIn Recruiter before navigating to the LinkedIn tab for a candidate in Attract.</span></span> <span data-ttu-id="e4da4-125">Użytkownik będzie mógł zobaczyć podstawowe dane profilu publicznego kandydata, takie jak imię i nazwisko.</span><span class="sxs-lookup"><span data-stu-id="e4da4-125">You'll be able to see the candidate's basic public profile data, such as their first and last name.</span></span>

1. <span data-ttu-id="e4da4-126">W Attract celu wybierz **Prace** lub **Pule talentów** po lewej stronie, a następnie wybierz kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4da4-126">In Attract, select **Jobs** or **Talent pools** on the left, and then select an applicant.</span></span>

    ![[<span data-ttu-id="e4da4-127">Wyświetlanie kandydatów LinkedIn w Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-127">View LinkedIn candidates in Attract</span></span>](./media/attract-view-linkedin-candidates.png)](./media/attract-view-linkedin-candidates.png)

2. <span data-ttu-id="e4da4-128">W profilu kandydata wybierz kartę **LinkedIn**. Można wyświetlić profil kandydata z historią InMail.</span><span class="sxs-lookup"><span data-stu-id="e4da4-128">In the candidate's profile, select the **LinkedIn** tab. You can view the candidate's profile and InMail history.</span></span>

   ![Wyświetl informacje dotyczące kandydata w serwisie LinkedIn](./media/attract-candidate-linkedin-tab.png)

<span data-ttu-id="e4da4-130">W tym oknie można wykonać następujące czynności:</span><span class="sxs-lookup"><span data-stu-id="e4da4-130">From here, you can perform the following actions:</span></span>

- <span data-ttu-id="e4da4-131">Wybierz **kartę działania rekrutacji**, aby wyświetlić:</span><span class="sxs-lookup"><span data-stu-id="e4da4-131">Select the **Recruiting activities** tab to view:</span></span>
   
   - <span data-ttu-id="e4da4-132">Notatki dotyczące rekrutacji (publiczne i prywatne).</span><span class="sxs-lookup"><span data-stu-id="e4da4-132">Recruiter notes (both public and private).</span></span> <span data-ttu-id="e4da4-133">Domyślnie notatki są prywatne i widoczne tylko dla właściciela notatek.</span><span class="sxs-lookup"><span data-stu-id="e4da4-133">By default, notes are private and only visible to the owner of the notes.</span></span>
   - <span data-ttu-id="e4da4-134">Aktywność InMail (ale nie zawartość InMail).</span><span class="sxs-lookup"><span data-stu-id="e4da4-134">InMail activity (but not the InMail content).</span></span> <span data-ttu-id="e4da4-135">Przewiń do dołu strony, aby wyświetlić InMail wymianę informacji z kandydatem i wyświetlić innych użytkowników w organizacji, którzy komunikują się z kandydatem.</span><span class="sxs-lookup"><span data-stu-id="e4da4-135">Scroll to the bottom of the page to view the InMail exchange with your prospect and view other users in your organization who are interacting with your prospect.</span></span>
   - <span data-ttu-id="e4da4-136">Działanie związane z odrzuceniem kandydata</span><span class="sxs-lookup"><span data-stu-id="e4da4-136">Candidate rejection activity</span></span>

- <span data-ttu-id="e4da4-137">Wybierz przycisk **Wyślij InMail**, aby wysłać wiadomość InMail bez konieczności opuszczania Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-137">Select **Send InMail** to send InMail without having to leave Attract.</span></span>

- <span data-ttu-id="e4da4-138">Wybierz opcję **Zapisz do zadania**, aby zapisać zadanie bez opuszczania Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-138">Select **Save to a job** to save the job without leaving Attract.</span></span>

> [!NOTE]
> <span data-ttu-id="e4da4-139">Profil LinkedIn kandydata zostanie wyświetlony w Attract, gdy informacje Attract kandydata będą zgodne z danymi LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e4da4-139">A candidate's LinkedIn profile will display in Attract when the candidate's Attract information matches the LinkedIn information.</span></span> <span data-ttu-id="e4da4-140">Oto stosowane reguły dopasowywania:</span><span class="sxs-lookup"><span data-stu-id="e4da4-140">Here are the matching rules that are used:</span></span>
> 
> 1. <span data-ttu-id="e4da4-141">Jeśli adres e-mail i identyfikator członka serwisu LinkedIn zgadzają się w Attract i LinkedIn, wyświetlany jest profil kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4da4-141">If the email address and LinkedIn member ID match in Attract and LinkedIn, the candidate's profile is shown.</span></span> <span data-ttu-id="e4da4-142">Kandydaci nadal mają możliwość łączenia lub odłączania profilu LinkedIn w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-142">Candidates still have the option to link or unlink their LinkedIn profile from Attract.</span></span>
> 2. <span data-ttu-id="e4da4-143">Jeśli adres e-mail lub identyfikator członka LinkedIn nie zgadza się, zostanie wyświetlona lista możliwych kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e4da4-143">If the email address or LinkedIn member ID doesn't match, you see a list of possible candidates.</span></span> <span data-ttu-id="e4da4-144">Następnie można wybrać kandydata z listy i połączyć profil.</span><span class="sxs-lookup"><span data-stu-id="e4da4-144">You can then select a candidate in the list and link the profile.</span></span>
> 3. <span data-ttu-id="e4da4-145">Jeśli nie ma żadnych dobrych odpowiedników, zostanie wyświetlone powiadomienie, że nie znaleziono odpowiednika.</span><span class="sxs-lookup"><span data-stu-id="e4da4-145">If there are no good matches, you're notified that no match was found.</span></span>

## <a name="export-linkedin-candidates-to-attract-with-one-click"></a><span data-ttu-id="e4da4-146">Eksportowanie kandydatów LinkedIn do Attract za pomocą jednego kliknięcia</span><span class="sxs-lookup"><span data-stu-id="e4da4-146">Export LinkedIn candidates to Attract with one click</span></span>

<span data-ttu-id="e4da4-147">Podczas przeglądania kandydatów w LinkedIn Recruiter można eksportować ich do aktualnie otwartych stanowisk w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-147">While you're reviewing candidates in LinkedIn Recruiter, you can export them to jobs that you currently have open in Attract.</span></span> <span data-ttu-id="e4da4-148">W tym kroku przyciąganie wymaga uprawnień Rekrutacja lub Menedżer zatrudniania w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-148">For this step, you need Recruiter or Hiring Manager permissions in Attract.</span></span> <span data-ttu-id="e4da4-149">Aby uzyskać więcej informacji o rolach w Attract, zobacz [Zarządzanie zabezpieczeniami i rolami w aplikacji Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).</span><span class="sxs-lookup"><span data-stu-id="e4da4-149">For more information about roles in Attract, see [Security and role management in Attract](https://docs.microsoft.com/dynamics365/unified-operations/talent/security-attract).</span></span>

<span data-ttu-id="e4da4-150">Należy również upewnić się, że zadanie ma etap prospektu.</span><span class="sxs-lookup"><span data-stu-id="e4da4-150">You must also make sure that the job has a Prospect stage.</span></span> <span data-ttu-id="e4da4-151">Aby uzyskać więcej informacji, zobacz [Działanie Prospekt](./activities-attract.md#prospect-activity).</span><span class="sxs-lookup"><span data-stu-id="e4da4-151">For more information, see [Prospect activity](./activities-attract.md#prospect-activity).</span></span>

1. <span data-ttu-id="e4da4-152">W Attract utwórz funkcję, przypisz odpowiednie role i aktywuj pracę.</span><span class="sxs-lookup"><span data-stu-id="e4da4-152">In Attract, create a job, assign the appropriate roles, and activate the job.</span></span>
2. <span data-ttu-id="e4da4-153">W LinkedIn Recruiter znajdź dobrego kandydata do pracy i przejdź do profilu kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4da4-153">In LinkedIn Recruiter, find a good candidate for the job, and go to the candidate's profile.</span></span>
3. <span data-ttu-id="e4da4-154">Używając pola wyszukiwania pracy na karcie kontaktu, znajdź pracę na podstawie tytułu lub identyfikatora pracy aktywowanego w aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-154">In the job search box in the contact card, find the job by using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="e4da4-155">Jeśli nie można znaleźć pracy, kliknij przycisk **Change ATS** (Zmień system ATS) i poszukaj prawidłowego wystąpienia aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-155">If you can't find the job, select **Change ATS** to find the correct Attract instance.</span></span>
4. <span data-ttu-id="e4da4-156">Wybierz stanowisko i kliknij przycisk **Eksportuj**.</span><span class="sxs-lookup"><span data-stu-id="e4da4-156">Select the job, and then select **Export**.</span></span>
5. <span data-ttu-id="e4da4-157">Otwórz pracę w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-157">In Attract, open the job.</span></span> <span data-ttu-id="e4da4-158">Wyeksportowany kandydat zostanie wyświetlony na karcie pracy **Prospekt**.</span><span class="sxs-lookup"><span data-stu-id="e4da4-158">The exported candidate will appear on the **Prospect** tab of the job.</span></span>

## <a name="view-attract-information-in-linkedin-recruiter"></a><span data-ttu-id="e4da4-159">Wyświetl informacje o Attract w LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="e4da4-159">View Attract information in LinkedIn Recruiter</span></span>

<span data-ttu-id="e4da4-160">W aplikacji LinkedIn Recruiter można śledzić, czy kandydat aplikował na inne stanowiska w Twojej organizacji, sprawdzić, na których etapach ubiegania się o pracę jest obecnie, oraz obejrzeć informacje zwrotne i komentarze z aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-160">In LinkedIn Recruiter, you can track whether a candidate applied to other jobs in your organization, see where the candidate is in the various stages for job applications, and view feedback and comments from Attract.</span></span>

1. <span data-ttu-id="e4da4-161">Otwórz LinkedIn Recruiter i wybierz profil kandydata.</span><span class="sxs-lookup"><span data-stu-id="e4da4-161">Open LinkedIn Recruiter, and select a candidate profile.</span></span>
2. <span data-ttu-id="e4da4-162">Umieść wskaźnik myszy na **W ATS**.</span><span class="sxs-lookup"><span data-stu-id="e4da4-162">Hover over **In ATS**.</span></span>
3. <span data-ttu-id="e4da4-163">Wybierz jedną z następujących opcji, aby wyświetlić informacje o kandydatach, które są przechowywane w Attract:</span><span class="sxs-lookup"><span data-stu-id="e4da4-163">Select any of the following options to view the candidate information that is stored in Attract:</span></span>

    - <span data-ttu-id="e4da4-164">**Prace i statusy** — wyświetlanie stanowisk, których częścią jest kandydat, najnowszego statusu i sposobu, etap procesu kandydata dla każdego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="e4da4-164">**Jobs & Statuses** – See jobs that the candidate is part of, the latest status, and how the candidate is progressing for each job.</span></span>
    - <span data-ttu-id="e4da4-165">**Opinie po rozmowach kwalifikacyjnych** – wyświetla opinie przesłane przez osoby prowadzące rozmowy kwalifikacyjne do aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-165">**Interview Feedback** – See feedback that interviewers have submitted in Attract.</span></span>
    - <span data-ttu-id="e4da4-166">**Notatki** — zajrzyj do notatek wprowadzonych dla tego kandydata w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-166">**Notes** – See any notes that have been entered for this candidate in Attract.</span></span>

    ![[<span data-ttu-id="e4da4-167">Wyświetl informacje Attract z LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="e4da4-167">View Attract information from LinkedIn Recruiter</span></span>](./media/attract-view-information-from-linkedin-recruiter.png)](./media/attract-view-information-from-linkedin-recruiter.png)

> [!NOTE]
> <span data-ttu-id="e4da4-168">Dane kandydata i aplikacji nie będą synchronizowane z usługą LinkedIn Recruiter, jeśli kandydat nie wyszedł poza etap Prospektu.</span><span class="sxs-lookup"><span data-stu-id="e4da4-168">Candidate and application data won't be synced with LinkedIn Recruiter if the candidate hasn't moved past the Prospect stage.</span></span>

## <a name="view-linkedin-talent-pools"></a><span data-ttu-id="e4da4-169">Wyświetlanie pul talentów w serwisie LinkedIn</span><span class="sxs-lookup"><span data-stu-id="e4da4-169">View LinkedIn talent pools</span></span>

<span data-ttu-id="e4da4-170">Jeśli kandydaci zgadzają się na udostępnianie swoich profilów LinkedIn innym użytkownikom w organizacji, zostanie utworzony nowy rekord kandydata w Attract.</span><span class="sxs-lookup"><span data-stu-id="e4da4-170">If candidates agree to share their LinkedIn profiles with any user in your organization, a new candidate record is created in Attract.</span></span> <span data-ttu-id="e4da4-171">Następnie te kandydaci znajdują się w puli talentów w systemie tworzonym w serwisie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e4da4-171">These candidates then appear in a system-created LinkedIn talent pool.</span></span>

1. <span data-ttu-id="e4da4-172">W Attract należy wybrać **pulę talentów** po lewej stronie.</span><span class="sxs-lookup"><span data-stu-id="e4da4-172">In Attract, select **Talent pools** on the left.</span></span>
2. <span data-ttu-id="e4da4-173">Wybierz pulę talentów serwisu LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e4da4-173">Select the LinkedIn talent pool.</span></span> <span data-ttu-id="e4da4-174">Zostanie wyświetlona lista kandydatów i ich profili szczątkowych z serwisu LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="e4da4-174">You will see a list of candidates and their stub profiles from LinkedIn.</span></span> <span data-ttu-id="e4da4-175">Profile szczątkowe zawierają imiona i nazwiska i adresy e-mail kandydata, jeśli kandydat pobrał opcję jego udostępnienia.</span><span class="sxs-lookup"><span data-stu-id="e4da4-175">Stub profiles contain the candidate's first and last names and email address, if the candidate chose to share it.</span></span>

## <a name="see-also"></a><span data-ttu-id="e4da4-176">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e4da4-176">See also</span></span>

[<span data-ttu-id="e4da4-177">Konfigurowanie integracji Attract z serwisem LinkedIn — często zadawane pytania</span><span class="sxs-lookup"><span data-stu-id="e4da4-177">Attract integration with LinkedIn FAQ</span></span>](./attract-linkedin-faq.md)

[<span data-ttu-id="e4da4-178">Konfigurowanie integracji z serwisem LinkedIn dla aplikacji Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-178">Set up integration with LinkedIn for Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-admin-linkedin.md)

[<span data-ttu-id="e4da4-179">Tworzenie, zatwierdzanie i publikowanie funkcji w aplikacji Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-179">Create, approve, and post jobs in Attract</span></span>](./creating-jobs-attract.md)

[<span data-ttu-id="e4da4-180">Publikowanie ofert pracy w serwisie LinkedIn z poziomu aplikacji Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-180">Post jobs to LinkedIn from Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-post-jobs-to-linkedin.md)

[<span data-ttu-id="e4da4-181">Rozwiązywanie problemów z integracją usługi LinkedIn i Microsoft Dynamics 365 Talent - Attract</span><span class="sxs-lookup"><span data-stu-id="e4da4-181">Troubleshooting integration with LinkedIn and Microsoft Dynamics 365 Talent - Attract</span></span>](./attract-troubleshoot-linkedin.md)
