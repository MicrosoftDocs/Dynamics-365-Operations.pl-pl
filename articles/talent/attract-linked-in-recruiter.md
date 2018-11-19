---
title: Korzystanie z aplikacji LinkedIn Recruiter
description: "Ten temat zawiera informacje o używaniu funkcji uczenia maszynowego do generowania rekomendacji funkcji i kandydatów na funkcje."
author: josaw
manager: AnnBe
ms.date: 10/15/2018
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
ms.sourcegitcommit: 2fc6bf25d303d7d8de8002a923a080b90dcfbeab
ms.openlocfilehash: 106103e2c3d8f3d89aac5140174e5794da22536f
ms.contentlocale: pl-pl
ms.lasthandoff: 10/24/2018

---

# <a name="sourcing-with-linkedin-recruiter"></a><span data-ttu-id="036b3-103">Korzystanie z aplikacji LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="036b3-103">Sourcing with LinkedIn Recruiter</span></span>
[!include[banner](../includes/banner.md)]

<span data-ttu-id="036b3-104">LinkedIn to największa na świecie baza danych pracowników i osób szukających pracy oraz często główny system, którego osoby rekrutujące używają do wyszukiwania, komunikowania się i pozyskiwania kandydatów na funkcje, które chcą obsadzić.</span><span class="sxs-lookup"><span data-stu-id="036b3-104">LinkedIn is the world’s largest talent database and often the primary system that recruiters use to find, communicate with, and source candidates for the jobs that recruiters are looking to fill.</span></span> <span data-ttu-id="036b3-105">Integracja aplikacji LinkedIn Recruiter z aplikacją Dynamics 365 for Talent Attract ułatwia użytkownikom zatrudnianie osób oraz synchronizowanie danych między oboma systemami.</span><span class="sxs-lookup"><span data-stu-id="036b3-105">LinkedIn Recruiter integration with Dynamics 365 for Talent: Attract makes it easier for users to hire, and to keep the data in sync between the two systems.</span></span>

> [!NOTE]
> <span data-ttu-id="036b3-106">Aby można było korzystać z integracji aplikacji LinkedIn Recruiter z aplikacją Attract, trzeba mieć dodatek kompleksowej obsługi rekrutacji oraz wykupione stanowiska w aplikacji LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-106">You need the Comprehensive hiring add-on and LinkedIn Recruiter seats to be able to use LinkedIn Recruiter integration with Attract.</span></span>

## <a name="set-up-linkedin-recruiter-with-attract"></a><span data-ttu-id="036b3-107">Konfigurowanie współdziałania aplikacji LinkedIn Recruiter z aplikacją Attract</span><span class="sxs-lookup"><span data-stu-id="036b3-107">Set up LinkedIn Recruiter with Attract</span></span> 

<span data-ttu-id="036b3-108">Zanim będzie można używać funkcji aplikacji LinkedIn Recruiter, należy skonfigurować dostęp na poziomie umowy lub firmy w wystąpieniu aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-108">Before you can use the LinkedIn Recruiter capabilities, you must configure contract-level or company-level access with your Attract instance.</span></span> <span data-ttu-id="036b3-109">W celu przeprowadzenia procesu konfiguracji należy współpracować z użytkownikiem, który jest administratorem umowy na usługę LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-109">To complete the configuration process, you must work with the user who is an Admin on your LinkedIn Recruiter contract.</span></span> <span data-ttu-id="036b3-110">Aby skonfigurować współdziałanie aplikacji LinkedIn Recruiter i Attract, wykonaj poniższe kroki.</span><span class="sxs-lookup"><span data-stu-id="036b3-110">Complete the following steps to configure LinkedIn Recruiter with Attract.</span></span>

1.  <span data-ttu-id="036b3-111">Zaloguj się w aplikacji Attract jako administrator i przejdź do okna **Ustawienia administratora**.</span><span class="sxs-lookup"><span data-stu-id="036b3-111">Sign in to Attract as an Admin and go to **Admin Settings**.</span></span>

2.  <span data-ttu-id="036b3-112">W lewym okienku kliknij kartę **Integracja z serwisem LinkedIn**.</span><span class="sxs-lookup"><span data-stu-id="036b3-112">On the left pane, click the **LinkedIn Integration** tab.</span></span>

<span data-ttu-id="036b3-113">[![Widok administratora aplikacji Attract przy rozpoczynaniu integracji z aplikacją LinkedIn Recruiter](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span><span class="sxs-lookup"><span data-stu-id="036b3-113">[![Attract Admin view to start LinkedIn Recruiter integration](./media/LinkedInConnect.png)](./media/LinkedInConnect.png)</span></span>

3.  <span data-ttu-id="036b3-114">Kliknij przycisk **Połącz**, aby uruchomić instalatora i zostać przeprowadzonym przez proces logowania do serwisu LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="036b3-114">Click **Connect** to start the setup and be guided through the LinkedIn sign-in process.</span></span>

4.  <span data-ttu-id="036b3-115">Jeśli masz stanowiska w różnych umowach na LinkedIn, zaznacz umowę, którą chcesz połączyć z systemem Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-115">If you have seats on multiple LinkedIn contracts, select the contract that you would like to connect to the Attract system.</span></span> <span data-ttu-id="036b3-116">Jeśli masz stanowisko tylko w jednej umowie na LinkedIn, ten krok nie będzie potrzebny.</span><span class="sxs-lookup"><span data-stu-id="036b3-116">If you have a seat on only one LinkedIn contract, this step will not be needed.</span></span>

5.  <span data-ttu-id="036b3-117">Widżet serwisu LinkedIn załaduje teraz Twoje ustawienia administratora z wyświetloną listą integracji.</span><span class="sxs-lookup"><span data-stu-id="036b3-117">The LinkedIn widget will now load in your Admin settings with the list of integrations shown.</span></span> <span data-ttu-id="036b3-118">W obszarze **Połącz z systemem Recruiter** kliknij przycisk **Poproś**.</span><span class="sxs-lookup"><span data-stu-id="036b3-118">Under **Recruiter System connect**, click **Request**.</span></span>

<span data-ttu-id="036b3-119">[![Widok administratora aplikacji Attract przy wnioskowaniu o integrację z aplikacją LinkedIn Recruiter](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span><span class="sxs-lookup"><span data-stu-id="036b3-119">[![Attract Admin view to Request LinkedIn Recruiter integration](./media/RequestLinkedInRSC.png)](./media/RequestLinkedInRSC.png)</span></span>

6.  <span data-ttu-id="036b3-120">Po wysłaniu prośby o integrację z aplikacji Attract aplikacja będzie wyświetlana jako **Gotowa do współpracy** i można ją włączyć z okna **Ustawienia administratora aplikacji Recruiter**.</span><span class="sxs-lookup"><span data-stu-id="036b3-120">After the integration is requested from Attract, it will show as **Partner ready** and is ready to be turned on from **Recruiter Admin settings**.</span></span> <span data-ttu-id="036b3-121">Jeśli na tej stronie zobaczysz przycisk **Powiadom partnera**, poczekaj kilka sekund, kliknij przycisk **Powiadom partnera**, a następnie odśwież stronę.</span><span class="sxs-lookup"><span data-stu-id="036b3-121">If you see **Notify partner** on this page, wait a few seconds, click **Notify partner**, and then refresh the page.</span></span> <span data-ttu-id="036b3-122">Napis powinien się zmienić na **Gotowa do współpracy**.</span><span class="sxs-lookup"><span data-stu-id="036b3-122">It should now show as **Partner ready**.</span></span>

<span data-ttu-id="036b3-123">[![Widok administratora aplikacji Attract wskazujący, że wszystkie żądania po stronie aplikacji Attract zostały wykonane](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span><span class="sxs-lookup"><span data-stu-id="036b3-123">[![Attract Admin view to indicate Attract side of requests have been completed](./media/PartnerReadyRSC.png)](./media/PartnerReadyRSC.png)</span></span>

<span data-ttu-id="036b3-124">Aby wykonać następny krok, musisz mieć uprawnienia administratora w umowie na usługę LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-124">To complete the next step, you need to have an Admin privilege on your LinkedIn Recruiter Contract.</span></span>

7.  <span data-ttu-id="036b3-125">Zaloguj się w serwisie LinkedIn przy użyciu konta administratora i przejdź do aplikacji LinkedIn Recruiter, klikając opcję w prawym górnym rogu.</span><span class="sxs-lookup"><span data-stu-id="036b3-125">Sign in to LinkedIn using the Admin account and go to LinkedIn Recruiter on the top right.</span></span> 

8. <span data-ttu-id="036b3-126">W menu **More** (Więcej) w górnej części ekranu kliknij przycisk **Admin Settings** (Ustawienia administratora), a następnie kliknij kartę **ATS**.</span><span class="sxs-lookup"><span data-stu-id="036b3-126">On the **More** menu at the top of the screen, click **Admin Settings**, and then click the **ATS** Tab.</span></span>

<span data-ttu-id="036b3-127">System Attract będzie wyświetlony z kilkoma opcjami, które można włączyć.</span><span class="sxs-lookup"><span data-stu-id="036b3-127">The Attract system will be listed with a couple of options that can be turned on.</span></span>

9. <span data-ttu-id="036b3-128">Jeśli chcesz włączyć tylko funkcję eksportu jednym kliknięciem dla **wskaźnika danych z systemu ATS** i **widżetu profilu danych z systemu ATS**, wybierz opcję **Company-level access** (Dostęp na poziomie firmy).</span><span class="sxs-lookup"><span data-stu-id="036b3-128">If you want to enable only 1-Click export for the **In-ATS indicator** and the **In-ATS Profile Widget**, select **Company-level access**.</span></span> <span data-ttu-id="036b3-129">Aby włączyć wszystkie funkcje dostępu na poziomie firmy oraz dostęp do historii wiadomości InMail, historii notatek i profilu szczątkowego InMail, wybierz opcję **Contract-level access** (Dostęp na poziomie umowy).</span><span class="sxs-lookup"><span data-stu-id="036b3-129">If you want to enable all of Company-level access features plus InMail history, Notes history, and the InMail stub profile access, select **Contract-level access**.</span></span>

10. <span data-ttu-id="036b3-130">Włącz żądany poziom dostępu w ustawieniach **administratora systemu ATS** w aplikacji LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-130">Turn on the desired access level from your LinkedIn Recruiter **Admin-ATS** settings.</span></span>

<span data-ttu-id="036b3-131">[![Włączanie integracji z aplikacją Attract z widoku administratora aplikacji LinkedIn Recruiter](./media/EnableRSC.png)](./media/EnableRSC.png)</span><span class="sxs-lookup"><span data-stu-id="036b3-131">[![Turn on Attract integration from LinkedIn Recruiter Admin view](./media/EnableRSC.png)](./media/EnableRSC.png)</span></span>

12. <span data-ttu-id="036b3-132">Wróć do okna ustawień administratora aplikacji Attract jako administrator aplikacji Attract i kliknij kartę **Integracja z serwisem LinkedIn**. Powinien być teraz widoczny załadowany widżet serwisu LinkedIn z podpisem **Włączone** oraz włączonym wybranym poziomem dostępu.</span><span class="sxs-lookup"><span data-stu-id="036b3-132">Go back to Attract Admin Settings as an AttractAdmin and select the **LinkedIn integration** tab. You should now see the LinkedIn widget load showing **Enabled** with the selected access level turned on.</span></span>

<span data-ttu-id="036b3-133">[![Integracja z aplikacją LinkedIn Recruiter zakończona](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span><span class="sxs-lookup"><span data-stu-id="036b3-133">[![LinkedIn Recruiter integration complete](./media/RSCSetupComplete.png)](./media/RSCSetupComplete.png)</span></span>

## <a name="using-linkedin-recruiter-capabilities"></a><span data-ttu-id="036b3-134">Używanie funkcji aplikacji LinkedIn Recruiter</span><span class="sxs-lookup"><span data-stu-id="036b3-134">Using LinkedIn Recruiter capabilities</span></span>

<span data-ttu-id="036b3-135">Gdy administrator aplikacji Attract włączy funkcje aplikacji LinkedIn Recruiter, będą one dostępne dla menedżerów zatrudniających i osób rekrutujących.</span><span class="sxs-lookup"><span data-stu-id="036b3-135">After LinkedIn Recruiter capabilities has been enabled by the Attract Admin it is available for hiring managers and recruiters to access.</span></span> <span data-ttu-id="036b3-136">Aby korzystać z tych funkcji, podłącz konto serwisu LinkedIn w obszarze **Ustawienia użytkownika**.</span><span class="sxs-lookup"><span data-stu-id="036b3-136">To use these capabilities, connect your LinkedIn account under **User Settings**.</span></span> <span data-ttu-id="036b3-137">Połączenie ustawień administratora i użytkownika spowoduje udostępnienie kilku funkcji.</span><span class="sxs-lookup"><span data-stu-id="036b3-137">Several capabilities will be available after both the Admin and User settings have been connected.</span></span>

### <a name="in-ats-profile-widget"></a><span data-ttu-id="036b3-138">Widżet profilu danych z systemu ATS</span><span class="sxs-lookup"><span data-stu-id="036b3-138">In-ATS profile widget</span></span>

<span data-ttu-id="036b3-139">W aplikacji Attract można wyświetlić profil kandydata z serwisu LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="036b3-139">You can view the candidate’s LinkedIn profile in Attract.</span></span> <span data-ttu-id="036b3-140">Widżet serwisu LinkedIn będzie pokazywał profil kandydata, jeśli informacje w systemie ATS pasują do danych użytkownika w serwisie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="036b3-140">The LinkedIn widget will display the candidate profile when the ATS information matches the LinkedIn information of its users.</span></span>

<span data-ttu-id="036b3-141">Aby wyświetlić profil kandydata, przejdź do niego z poziomu stanowiska lub puli umiejętności.</span><span class="sxs-lookup"><span data-stu-id="036b3-141">To view a profile, go the candidate profile either from a job or talent pool.</span></span> <span data-ttu-id="036b3-142">W profilu kandydata kliknij kartę **LinkedIn**, a widżet profilu zostanie załadowany.</span><span class="sxs-lookup"><span data-stu-id="036b3-142">In the candidate profile, select the **LinkedIn** tab and the profile widget will load.</span></span> <span data-ttu-id="036b3-143">Za pomocą widżetu profilu wskaż, czy jest to pasująca osoba.</span><span class="sxs-lookup"><span data-stu-id="036b3-143">Using the profile widget, indicate if this is the correct match.</span></span> <span data-ttu-id="036b3-144">Jeśli nie, znajdź prawidłową osobę.</span><span class="sxs-lookup"><span data-stu-id="036b3-144">If it is not, find the correct person.</span></span> <span data-ttu-id="036b3-145">Z tej strony można również zapisać kandydata do projektów w usłudze LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-145">You can also save the candidate to your LinkedIn Recruiter projects from this page.</span></span>

### <a name="1-click-export"></a><span data-ttu-id="036b3-146">Eksport jednym kliknięciem</span><span class="sxs-lookup"><span data-stu-id="036b3-146">1-click export</span></span> 

<span data-ttu-id="036b3-147">W trakcie pozyskiwania kandydatów z serwisu LinkedIn można jednym kliknięciem wyeksportować kandydata do aktualnie otwartych funkcji.</span><span class="sxs-lookup"><span data-stu-id="036b3-147">While sourcing candidates in LinkedIn, you can 1-click export the candidate to the jobs that you currently have open.</span></span> <span data-ttu-id="036b3-148">Aby skonfigurować funkcję eksportu jednym kliknięciem, wykonaj kroki opisane poniżej.</span><span class="sxs-lookup"><span data-stu-id="036b3-148">Complete the following steps for a 1-click export.</span></span> <span data-ttu-id="036b3-149">Przed wykonaniem tych czynności upewnij się, że masz przypisaną rolę Menedżer zatrudniający lub Osoba rekrutująca wobec funkcji, a funkcja jest na etapie **Prospekt**.</span><span class="sxs-lookup"><span data-stu-id="036b3-149">Before you complete these steps, verify that you are a assigned the role of Hiring manager or Recruiter for the job and that the job has a **Prospect** stage.</span></span>

1.  <span data-ttu-id="036b3-150">Utwórz funkcję, przypisz odpowiednie role i aktywuj funkcję.</span><span class="sxs-lookup"><span data-stu-id="036b3-150">Create the job, assign the appropriate roles, and activate the job.</span></span>

2.  <span data-ttu-id="036b3-151">Po uaktywnieniu funkcji przejdź do aplikacji LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-151">When the job is activated, navigate to LinkedIn Recruiter.</span></span>

3.  <span data-ttu-id="036b3-152">Odszukaj żądanego kandydata i przejdź do jego profilu.</span><span class="sxs-lookup"><span data-stu-id="036b3-152">Find the candidate that you are looking for and go to their profile.</span></span>

4.  <span data-ttu-id="036b3-153">Używając pola wyszukiwania funkcji na karcie kontaktu, znajdź funkcję na podstawie tytułu lub identyfikatora funkcji aktywowanego w aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-153">Using the job search box in the contact card, find the job using the title or the Job ID that was activated in Attract.</span></span> <span data-ttu-id="036b3-154">Jeśli nie można znaleźć funkcji, kliknij przycisk **Change ATS** (Zmień system ATS) i poszukaj prawidłowego wystąpienia aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-154">If you don’t find the job, click **Change ATS** to find the correct Attract instance.</span></span>

5. <span data-ttu-id="036b3-155">Po wybraniu funkcji kliknij przycisk **Export** (Eksportuj).</span><span class="sxs-lookup"><span data-stu-id="036b3-155">After the job is selected, click **Export**.</span></span> <span data-ttu-id="036b3-156">Kandydat został teraz pobrany przez aplikację Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-156">The candidate is now fetched by Attract.</span></span>

6.  <span data-ttu-id="036b3-157">Przejdź do aplikacji Attract i otwórz odnośną funkcję.</span><span class="sxs-lookup"><span data-stu-id="036b3-157">Go to Attract and open the respective job.</span></span> <span data-ttu-id="036b3-158">Wyeksportowany kandydat będzie widoczny w funkcji na etapie **Prospekt**.</span><span class="sxs-lookup"><span data-stu-id="036b3-158">You will find the candidate that you just exported in the **Prospect** stage of the job.</span></span>

### <a name="in-ats-indicator"></a><span data-ttu-id="036b3-159">Wskaźnik danych z systemu ATS</span><span class="sxs-lookup"><span data-stu-id="036b3-159">In-ATS indicator</span></span> 

<span data-ttu-id="036b3-160">W aplikacji LinkedIn Recruiter można śledzić, czy kandydat aplikował na inne funkcje w Twojej organizacji, sprawdzić, na których etapach ubiegania się o pracę jest obecnie, oraz obejrzeć informacje zwrotne i komentarze z aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-160">Using LinkedIn recruiter, you can track whether a candidate has applied to other jobs in your organization, look at where they are in different stages of job applications, and view the feedback and comments from Attract in LinkedIn Recruiter.</span></span>

1.  <span data-ttu-id="036b3-161">Otwórz aplikację LinkedIn Recruiter i znajdź profil żądanego kandydata.</span><span class="sxs-lookup"><span data-stu-id="036b3-161">Open LinkedIn Recruiter and locate the candidate profile that you are looking for.</span></span>

2.  <span data-ttu-id="036b3-162">Przewiń profil kandydata w dół do sekcji **In-ATS** (Dane z systemu ATS).</span><span class="sxs-lookup"><span data-stu-id="036b3-162">Scroll down to view the **In-ATS** section on the candidate’s profile.</span></span>

3.  <span data-ttu-id="036b3-163">Za pomocą tego widżetu można w widoku aplikacji LinkedIn Recruiter wyświetlić wszystkie informacje o kandydacie, które znajdują się w aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-163">You can use this widget to view all of the information about the candidate that’s present in Attract from within the LinkedIn Recruiter view.</span></span>

4.  <span data-ttu-id="036b3-164">Kliknij kartę **Jobs & Statuses** (Funkcje i statusy), aby wyświetlić funkcje zajmowane przez kandydata, jego najnowszy status oraz zachowanie na poszczególnych funkcjach.</span><span class="sxs-lookup"><span data-stu-id="036b3-164">Select the **Jobs & Statuses** tab to see jobs they are part of, the latest status, and how they have been moving against each job.</span></span>

5.  <span data-ttu-id="036b3-165">Na karcie **Interview Feedback** (Opinie po rozmowach kwalifikacyjnych) widać opinie przesłane przez osoby prowadzące rozmowy kwalifikacyjne do aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-165">Select the **Interview Feedback** tab to see feedback that the interviewers have submitted in Attract.</span></span>

6.  <span data-ttu-id="036b3-166">Na karcie **Notes** (Uwagi) widać notatki sporządzone o tym kandydacie w aplikacji Attract.</span><span class="sxs-lookup"><span data-stu-id="036b3-166">Select the **Notes** tab to see notes that have been captured for this applicant in Attract.</span></span>

### <a name="inmail-history"></a><span data-ttu-id="036b3-167">Historia wiadomości InMail</span><span class="sxs-lookup"><span data-stu-id="036b3-167">InMail history</span></span>

<span data-ttu-id="036b3-168">Historia wiadomości InMail w serwisie LinkedIn jest aktywna przy dostępie na poziomie umowy do usługi LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-168">The LinkedIn InMail history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="036b3-169">Po włączeniu tej opcji można przeglądać całą historię wiadomości InMail wymienianych z kandydatem.</span><span class="sxs-lookup"><span data-stu-id="036b3-169">When it is enabled, you can view your entire InMail history with the candidate.</span></span> <span data-ttu-id="036b3-170">Można także sprawdzić, kto jeszcze z organizacji komunikował się z kandydatem za pomocą wiadomości InMail, jednak nie można wyświetlić treści tych wiadomości.</span><span class="sxs-lookup"><span data-stu-id="036b3-170">You can also see who else from your organization has exchanged InMail with the candidate, however you can't view the messages between them.</span></span>

<span data-ttu-id="036b3-171">Aby wyświetlić historię wiadomości InMail, przejdź do profilu kandydata, przejdź do karty **LinkedIn** i przewiń do dołu strony.</span><span class="sxs-lookup"><span data-stu-id="036b3-171">To view InMail history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="036b3-172">Historię wiadomości InMail można wyświetlić tylko wtedy, gdy kandydat odpowiedział na Twoją prośbę i udostępnił Ci swój profil w serwisie LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="036b3-172">You can view the InMail history only if the candidate has responded to your request and chosen to share their profile with you in LinkedIn.</span></span> <span data-ttu-id="036b3-173">Wiadomości InMail są synchronizowane z aplikacją Attract co kilka godzin.</span><span class="sxs-lookup"><span data-stu-id="036b3-173">The messages from InMail sync with Attract every couple of hours.</span></span>

### <a name="notes-history"></a><span data-ttu-id="036b3-174">Historia notatek</span><span class="sxs-lookup"><span data-stu-id="036b3-174">Notes history</span></span> 

<span data-ttu-id="036b3-175">Historia notatek w serwisie LinkedIn jest aktywna przy dostępie na poziomie umowy do usługi LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-175">The LinkedIn notes history is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="036b3-176">Po włączeniu tej opcji można wyświetlać notatki sporządzone o kandydacie przez różne osoby rekrutujące z Twojej organizacji.</span><span class="sxs-lookup"><span data-stu-id="036b3-176">When it is enabled, you can view the notes that have been captured about the candidate by different recruiters from your organization.</span></span>

<span data-ttu-id="036b3-177">Aby wyświetlić historię notatek, przejdź do profilu kandydata, przejdź do karty **LinkedIn** i przewiń do dołu strony.</span><span class="sxs-lookup"><span data-stu-id="036b3-177">To view Notes history, go to a candidate’s profile, go to the **LinkedIn** tab and scroll to the bottom of the page to view the history.</span></span> <span data-ttu-id="036b3-178">W aplikacji LinkedIn Recruiter można przeglądać wszystkie notatki o kandydacie.</span><span class="sxs-lookup"><span data-stu-id="036b3-178">You can view all the notes about the candidate from LinkedIn Recruiter.</span></span>

### <a name="inmail-stub-profile"></a><span data-ttu-id="036b3-179">Profil szczątkowy InMail</span><span class="sxs-lookup"><span data-stu-id="036b3-179">InMail stub profile</span></span>

<span data-ttu-id="036b3-180">Profil szczątkowy InMail jest aktywny przy dostępie na poziomie umowy do usługi LinkedIn Recruiter.</span><span class="sxs-lookup"><span data-stu-id="036b3-180">The InMail stub profile is available with contract-level access with LinkedIn Recruiter.</span></span> <span data-ttu-id="036b3-181">Jeśli kandydaci zgodzą się udostępnić swoje profile z serwisu LinkedIn któremukolwiek użytkownikowi w Twojej organizacji, możesz śledzić tych kandydatów w aplikacji Attract, a dla każdego kandydata zostanie utworzony nowy rekord kandydata.</span><span class="sxs-lookup"><span data-stu-id="036b3-181">If candidates agree to share their LinkedIn profiles with any user in your organization, you can track the candidates in Attract and a new candidate record will be created for each candidate.</span></span>

<span data-ttu-id="036b3-182">Aby wyświetlić listę kandydatów, przejdź do okna **Pule umiejętności**, a zobaczysz listę pul umiejętności utworzoną w usłudze LinkedIn przez system.</span><span class="sxs-lookup"><span data-stu-id="036b3-182">To view the list of candidates, go to **Talent pools** to see a system-created LinkedIn talent pool.</span></span> <span data-ttu-id="036b3-183">Ta pula umiejętności zawiera listę kandydatów i ich profile szczątkowe otrzymane z serwisu LinkedIn, tylko z imionami i nazwiskami kandydatów.</span><span class="sxs-lookup"><span data-stu-id="036b3-183">This talent pool contains the list candidates and their stub profiles as received from LinkedIn, showing the candidate's first name and last name.</span></span> <span data-ttu-id="036b3-184">Identyfikator e-mail kandydata będzie widoczny tylko wtedy, gdy udostępnił on swój adres e-mail.</span><span class="sxs-lookup"><span data-stu-id="036b3-184">The candidate’s email ID will be displayed if the candidate had chosen to share their email address.</span></span>

