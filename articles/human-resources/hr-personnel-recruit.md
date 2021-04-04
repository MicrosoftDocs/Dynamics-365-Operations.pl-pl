---
title: Rekrutowanie kandydatów
description: Ten temat dotyczy sposobu rekrutacji kandydatów w Dynamics 365 Human Resources.
author: andreabichsel
manager: tfehr
ms.date: 12/03/2020
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
ms.author: anbichse
ms.search.validFrom: 2020-12-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 6aca285133495dfe023dfd18bdeb050aabcafee6
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/19/2021
ms.locfileid: "5478291"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="4fbd6-103">Rekrutowanie kandydatów</span><span class="sxs-lookup"><span data-stu-id="4fbd6-103">Recruit job candidates</span></span>

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

<span data-ttu-id="4fbd6-104">Dynamics 365 Human Resources ułatwia zarządzanie wnioskami o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="4fbd6-105">Usprawnia również przejście od kandydata do pracownika.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="4fbd6-106">Jeśli Twoja organizacja korzysta z oddzielnej aplikacji do rekrutacji, proces rekrutacji może obejmować następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="4fbd6-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="4fbd6-107">Wprowadzanie wniosku o rekrutację w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="4fbd6-108">Przekazywanie polecanych kandydatów do modułu Human Resources z aplikacji do rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="4fbd6-109">Zakończenie procesu zatwierdzania kandydata w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="4fbd6-110">W przypadku braku oddzielnej aplikacji do rekrutacji kandydatami w module Human Resources można również zarządzać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="4fbd6-111">Jeśli jesteś administratorem lub deweloperem i chcesz zintegrować moduł Human Resources z aplikacją do rekrutacji innego producenta, zobacz [Konfigurowanie integracji usługi Dataverse](hr-admin-integration-common-data-service.md) i [Konfigurowanie tabel wirtualnych usługi Dataverse](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="4fbd6-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Dataverse integration](hr-admin-integration-common-data-service.md) and [Configure Dataverse virtual tables](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="4fbd6-112">Aplikacje do integracji rekrutacji można również znaleźć na stronie [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="4fbd6-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="4fbd6-113">Aby wypróbować funkcję w wersji zapoznawczej do integracji z usługą LinkedIn Talent Hub, zobacz [Integracja z usługą LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="4fbd6-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="4fbd6-114">Włącz wnioski o rekrutację</span><span class="sxs-lookup"><span data-stu-id="4fbd6-114">Enable recruiting requests</span></span>

<span data-ttu-id="4fbd6-115">Aby przesyłać wnioski o rekrutację w module Human Resources, należy najpierw włączyć tę funkcję w **Udostępnionych parametrach modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources shared parameters**.</span></span>

1. <span data-ttu-id="4fbd6-116">W obszarze roboczym **Zarządzanie personelem** wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="4fbd6-117">W obszarze **Konfiguracja** wybierz opcję **Udostępniane parametry zasobów ludzkich**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-117">Under **Setup**, select **Human resources shared parameters**.</span></span>

3. <span data-ttu-id="4fbd6-118">Na karcie **Rekrutacja** w obszarze **REKRUTACJA** przy opcji **Włącz wnioski o rekrutację** ustaw **Tak**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-118">On the **Recruitment** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="4fbd6-119">Dodawanie lokalizacji wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="4fbd6-119">Add a recruiting request location</span></span>

<span data-ttu-id="4fbd6-120">Jeśli organizacja ma wiele lokalizacji, można je dodać, tak aby wnioskodawca mógł wybrać lokalizację, w której będzie pracowała nowa osoba.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-120">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="4fbd6-121">Lokalizacja zostanie uwzględniona w publikacji oferty pracy.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-121">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="4fbd6-122">Na pasku wyszukiwania wprowadź **lokalizację wniosku o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-122">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="4fbd6-123">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-123">Select **New**.</span></span>

3. <span data-ttu-id="4fbd6-124">W polu **Lokalizacja wniosku o rekrutację** wprowadź nazwę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-124">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Dodawanie lokalizacji wniosku o rekrutację](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="4fbd6-126">W polu **Opis** wprowadź opis lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-126">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="4fbd6-127">W obszarze **Lokalizacja** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-127">Under **Location**, select **Add**.</span></span> <span data-ttu-id="4fbd6-128">Jeśli pojawi się okno **Nowy adres**, wprowadź adres lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-128">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Wprowadź adres](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="4fbd6-130">W obszarze **Informacje kontaktowe** wprowadź dane osoby do kontaktu w tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-130">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="4fbd6-131">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-131">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="4fbd6-132">Dodawanie wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="4fbd6-132">Add a recruiting request</span></span>

<span data-ttu-id="4fbd6-133">Menedżerowie mogą przesyłać wnioski o rekrutację w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-133">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="4fbd6-134">W przypadku korzystania z oddzielnej aplikacji do rekrutacji wykonanie tych kroków spowoduje wysłanie wniosku o rekrutację i rozpoczęcie procesu rekrutacji w tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-134">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="4fbd6-135">W przeciwnym razie procedura ta po prostu rozpocznie wewnętrzny proces rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-135">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="4fbd6-136">Wybierz opcję **Samoobsługa pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-136">Select **Employee self service**.</span></span>

2. <span data-ttu-id="4fbd6-137">Wybierz kartę **Mój zespół**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-137">Select the **My team** tab.</span></span>

3. <span data-ttu-id="4fbd6-138">Wybierz **Złóż wniosek o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-138">Select  **Request to recruit**.</span></span>

   ![Uruchamianie wniosku o rekrutację](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="4fbd6-140">Wypełnij pola **Opis**, **Stanowisko** i **Szacowana data rozpoczęcia**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-140">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Zakończenie tworzenia wniosku o rekrutację](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="4fbd6-142">Kliknij przycisk **Kontynuuj**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-142">Select **Continue**.</span></span> <span data-ttu-id="4fbd6-143">Wniosek o rekrutację na dane stanowisko zostanie utworzony.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-143">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="4fbd6-144">W obszarze **Ogólne** wybierz osobę rekrutującą z listy rozwijanej **Osoba rekrutująca**, a następnie wybierz lokalizację z listy rozwijanej **Lokalizacja wniosku o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-144">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="4fbd6-145">W obszarze **Stanowisko** zmień informacje zależnie od potrzeb, a następnie wybierz opcję **Utwórz szczegóły ze stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-145">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Utwórz szczegóły ze stanowiska](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="4fbd6-147">Pozostała część wniosku o rekrutację zostanie wypełniona domyślnymi informacjami dotyczącymi danego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-147">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="4fbd6-148">W obszarze **Zewnętrzny opis** wprowadź opis stanowiska do udostępnienia poza firmą.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-148">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="4fbd6-149">W obszarze **Stanowiska** wybierz opcję **Dodaj**, a następnie wybierz stanowisko dla danego wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-149">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Dodawanie stanowiska](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="4fbd6-151">W obszarze **Umiejętności** wybierz opcję **Dodaj**, a następnie wybierz umiejętność.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-151">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="4fbd6-152">W obszarze **Wymagane wykształcenie** wybierz opcję **Dodaj**, a następnie wybierz wartości z list rozwijanych **Wykształcenie** i **Poziom wykształcenia**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-152">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Dodawanie wymagań dotyczących wykształcenia](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="4fbd6-154">W obszarze **Komentarz** dodaj opcjonalne uwagi.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-154">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="4fbd6-155">W obszarze **Wynagrodzenie** wybierz poziom z listy rozwijanej **Poziom**, a następnie odpowiednio dostosuj **Próg niski**, **Punkt kontrolny** i **Próg wysoki**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-155">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="4fbd6-156">Gdy wniosek o rekrutację będzie gotowy i można rozpocząć proces rekrutacji, wybierz opcję **Uaktywnij** na pasku menu.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-156">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Aktywacja wniosku o rekrutację](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="4fbd6-158">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-158">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="4fbd6-159">Wyświetlanie i edytowanie wniosków o rekrutację</span><span class="sxs-lookup"><span data-stu-id="4fbd6-159">View and edit your recruiting requests</span></span>

<span data-ttu-id="4fbd6-160">Jeśli jesteś menedżerem i chcesz wyświetlić swoje własne wnioski:</span><span class="sxs-lookup"><span data-stu-id="4fbd6-160">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="4fbd6-161">Wybierz opcję **Samoobsługa pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-161">Select **Employee self service**.</span></span>

2. <span data-ttu-id="4fbd6-162">Wybierz kartę **Mój zespół**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-162">Select the **My team** tab.</span></span>

3. <span data-ttu-id="4fbd6-163">W obszarze **Informacje dotyczące mojego zespołu** wybierz kartę **Wnioski o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-163">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Wybierz kartę Wnioski o rekrutację](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="4fbd6-165">Aby wyświetlić lub edytować wniosek o rekrutację, należy wybrać go z tabeli.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-165">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="4fbd6-166">Jeśli jesteś pracownikiem działu kadr i chcesz przejrzeć wszystkie wnioski o rekrutację:</span><span class="sxs-lookup"><span data-stu-id="4fbd6-166">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="4fbd6-167">Wybierz **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-167">Select **Personnel management**.</span></span>

2. <span data-ttu-id="4fbd6-168">Wybierz **Wnioski o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-168">Select **Recruiting requests**.</span></span>

   ![Wyświetlanie wniosków o rekrutację na stronie Zarządzanie personelem](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="4fbd6-170">Aby wyświetlić lub edytować wniosek o rekrutację, należy wybrać go z tabeli.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-170">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="4fbd6-171">Dodawanie lub edytowanie profilu kandydata</span><span class="sxs-lookup"><span data-stu-id="4fbd6-171">Add or edit a candidate profile</span></span>

<span data-ttu-id="4fbd6-172">Jeśli zarządzanie wnioskami o rekrutację zostało zintegrowane z inną aplikacją, to wnioski są przekazywane do tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-172">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="4fbd6-173">Następnie aplikacja do rekrutacji wysyła informacje o kandydatach do modułu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-173">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="4fbd6-174">W przeciwnym razie możesz postępować zgodnie z wewnętrznym procesem rekrutacji oraz wprowadzać dane kandydatów ręcznie.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-174">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="4fbd6-175">Wybierz **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-175">Select **Personnel management**.</span></span>

2. <span data-ttu-id="4fbd6-176">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-176">Select **Links**.</span></span>

3. <span data-ttu-id="4fbd6-177">W obszarze **Rekrutacja** wybierz opcję **Kandydaci**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-177">Under **Recruiting**, select **Candidates**.</span></span>

   ![Wyświetlanie kandydatów](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="4fbd6-179">Aby dodać kandydata, wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-179">To add a candidate, select **New**.</span></span> <span data-ttu-id="4fbd6-180">Aby edytować dane istniejącego kandydata, wybierz go z listy i wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-180">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="4fbd6-181">Zostanie wyświetlony profil kandydata.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-181">The candidate profile appears.</span></span>

5. <span data-ttu-id="4fbd6-182">W obszarze **Podsumowanie dotyczące kandydata** wprowadź lub zmień odpowiednie dane kandydatów.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-182">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="4fbd6-183">W obszarze **Wniosek o rekrutację** wybierz wniosek o rekrutację, z którym ma być połączony kandydat.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-183">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="4fbd6-184">Następnie wypełnij pola **Szacunkowa data rozpoczęcia**, **Menedżer zatrudniający**, **Stanowisko** i **Opis**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-184">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Łączenie z wnioskiem o rekrutację](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="4fbd6-186">Uzupełnij wszystkie informacje w następujących obszarach, które chcesz uwzględnić w rekordzie kandydata:</span><span class="sxs-lookup"><span data-stu-id="4fbd6-186">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="4fbd6-187">**Komentarze**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-187">**Comments**</span></span>
   - <span data-ttu-id="4fbd6-188">**Doświadczenie zawodowe**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-188">**Professional experience**</span></span>
   - <span data-ttu-id="4fbd6-189">**Informacje o kontakcie**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-189">**Contact information**</span></span>
   - <span data-ttu-id="4fbd6-190">**Wykształcenie**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-190">**Education**</span></span>
   - <span data-ttu-id="4fbd6-191">**Umiejętności**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-191">**Skills**</span></span>
   - <span data-ttu-id="4fbd6-192">**Certyfikaty**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-192">**Certificates**</span></span>
   - <span data-ttu-id="4fbd6-193">**Kontrole**</span><span class="sxs-lookup"><span data-stu-id="4fbd6-193">**Screenings**</span></span>

8. <span data-ttu-id="4fbd6-194">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-194">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="4fbd6-195">Zatrudnianie kandydata</span><span class="sxs-lookup"><span data-stu-id="4fbd6-195">Hire a candidate</span></span>

<span data-ttu-id="4fbd6-196">Gdy firma jest gotowa do zatrudnienia kandydata, wykonaj poniższe kroki, aby zmienić kandydata w pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-196">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="4fbd6-197">W formularzu kandydata wybierz **Zatrudnij**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-197">On the candidate form, select **Hire**.</span></span>

   ![Zatrudnianie kandydata](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="4fbd6-199">Wypełnij wszystkie pola w formularzu **Zatrudnij nowego pracownika** w obszarze **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-199">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Wprowadzanie danych dotyczących zatrudnianej osoby](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="4fbd6-201">Sprawdź dane w obszarze **Szczegóły dotyczące stanowiska** i zmodyfikuj je w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-201">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="4fbd6-202">W obszarze **Listy kontrolne wdrażania do pracy** wybierz odpowiednie listy kontrolne dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-202">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="4fbd6-203">Wybierz **Kontynuuj**, aby utworzyć rekord pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-203">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="4fbd6-204">W zależności od procedur w organizacji mogą być wymagane dodatkowe kroki zatwierdzania rekordu kandydata, zanim stanie się on rekordem pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-204">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="4fbd6-205">Decyzja o niezatrudnianiu kandydata</span><span class="sxs-lookup"><span data-stu-id="4fbd6-205">Decide not to hire a candidate</span></span>

<span data-ttu-id="4fbd6-206">W przypadku decyzji o niezatrudnianiu kandydata postępuj zgodnie z poniższą instrukcją, aby wykluczyć go z procesu weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-206">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="4fbd6-207">W formularzu kandydata wybierz **Nie zatrudniaj**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-207">On the candidate form, select **Do not hire**.</span></span>

   ![Niezatrudnianie kandydata](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="4fbd6-209">Wybierz **Kod przyczyny** i dodaj swoje uwagi.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-209">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="4fbd6-210">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-210">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="4fbd6-211">Odrzucanie kandydata</span><span class="sxs-lookup"><span data-stu-id="4fbd6-211">Dismiss a candidate</span></span>

<span data-ttu-id="4fbd6-212">Jeśli zajdzie potrzeba, można odrzucić kandydata po jego zatrudnieniu.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-212">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="4fbd6-213">Na przykład kandydat może wycofać swoją ofertę lub nie stawić się w pracy pierwszego dnia.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-213">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="4fbd6-214">W formularzu kandydata wybierz **Odrzuć kandydata**.</span><span class="sxs-lookup"><span data-stu-id="4fbd6-214">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Odrzuć kandydata](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="4fbd6-216">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="4fbd6-216">See also</span></span>

[<span data-ttu-id="4fbd6-217">Konfiguruj tabele wirtualne usługi Dataverse</span><span class="sxs-lookup"><span data-stu-id="4fbd6-217">Configure Dataverse virtual tables</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="4fbd6-218">Organizowanie pracowników</span><span class="sxs-lookup"><span data-stu-id="4fbd6-218">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="4fbd6-219">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="4fbd6-219">Set up the components of a job</span></span>](hr-personnel-jobs.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
