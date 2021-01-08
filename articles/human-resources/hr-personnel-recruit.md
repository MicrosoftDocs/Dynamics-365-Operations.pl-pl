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
ms.openlocfilehash: 9a35abcb8a2f6aa8031c8d84a44c2a8ad93883ac
ms.sourcegitcommit: 0354ca7e566fbd2eb0aabdd40000d4ac5c44ea78
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/04/2020
ms.locfileid: "4669185"
---
# <a name="recruit-job-candidates"></a><span data-ttu-id="e8105-103">Rekrutowanie kandydatów</span><span class="sxs-lookup"><span data-stu-id="e8105-103">Recruit job candidates</span></span>

[!include [banner](includes/preview-feature.md)]

<span data-ttu-id="e8105-104">Dynamics 365 Human Resources ułatwia zarządzanie wnioskami o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="e8105-104">Dynamics 365 Human Resources helps you to manage recruiting requests.</span></span> <span data-ttu-id="e8105-105">Usprawnia również przejście od kandydata do pracownika.</span><span class="sxs-lookup"><span data-stu-id="e8105-105">It also helps you seamlessly transition job candidates to employees.</span></span> <span data-ttu-id="e8105-106">Jeśli Twoja organizacja korzysta z oddzielnej aplikacji do rekrutacji, proces rekrutacji może obejmować następujące kroki:</span><span class="sxs-lookup"><span data-stu-id="e8105-106">If your organization uses a separate recruiting application, your recruiting process might include the following steps:</span></span>

- <span data-ttu-id="e8105-107">Wprowadzanie wniosku o rekrutację w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e8105-107">Enter your recruiting request in Human Resources.</span></span>
- <span data-ttu-id="e8105-108">Przekazywanie polecanych kandydatów do modułu Human Resources z aplikacji do rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-108">Receive candidate referrals in Human Resources from the recruiting application.</span></span>
- <span data-ttu-id="e8105-109">Zakończenie procesu zatwierdzania kandydata w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e8105-109">Complete the candidate approval process in Human Resources.</span></span>

<span data-ttu-id="e8105-110">W przypadku braku oddzielnej aplikacji do rekrutacji kandydatami w module Human Resources można również zarządzać ręcznie.</span><span class="sxs-lookup"><span data-stu-id="e8105-110">If you aren't using a separate recruiting application, you can also manually manage candidates in Human Resources.</span></span>

>[!NOTE]
><span data-ttu-id="e8105-111">Jeśli jesteś administratorem lub deweloperem i chcesz zintegrować moduł Human Resources z aplikacją do rekrutacji innego producenta, zobacz [Konfigurowanie integracji usługi Common Data Service](hr-admin-integration-common-data-service.md) i [Konfigurowanie jednostek wirtualnych usługi Common Data Service](hr-admin-integration-common-data-service-virtual-entities.md)</span><span class="sxs-lookup"><span data-stu-id="e8105-111">If you're an admin or developer and want to integrate Human Resources with a third-party recruiting application, see [Configure Common Data Service integration](hr-admin-integration-common-data-service.md) and [Configure Common Data Service virtual entities](hr-admin-integration-common-data-service-virtual-entities.md)</span></span>
>
> <span data-ttu-id="e8105-112">Aplikacje do integracji rekrutacji można również znaleźć na stronie [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span><span class="sxs-lookup"><span data-stu-id="e8105-112">You can also find recruiting integration apps on [AppSource](https://appsource.microsoft.com/marketplace/apps?search=recruiting%20dynamics).</span></span>
>
> <span data-ttu-id="e8105-113">Aby wypróbować funkcję w wersji zapoznawczej do integracji z usługą LinkedIn Talent Hub, zobacz [Integracja z usługą LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span><span class="sxs-lookup"><span data-stu-id="e8105-113">To try out our preview feature for integrating with LinkedIn Talent Hub, see [Integrate with LinkedIn Talent Hub](hr-admin-integration-linkedin.md).</span></span>

## <a name="enable-recruiting-requests"></a><span data-ttu-id="e8105-114">Włącz wnioski o rekrutację</span><span class="sxs-lookup"><span data-stu-id="e8105-114">Enable recruiting requests</span></span>

<span data-ttu-id="e8105-115">Aby przesyłać wnioski o rekrutację w module Human Resources, należy najpierw włączyć tę funkcję w **Parametrach modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="e8105-115">If you want to submit recruiting requests in Human Resources, you must first enable the functionality in **Human resources parameters**.</span></span>

1. <span data-ttu-id="e8105-116">W obszarze roboczym **Zarządzanie personelem** wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="e8105-116">In the **Personnel management** workspace, select **Links**.</span></span>

2. <span data-ttu-id="e8105-117">W obszarze **Konfiguracja** wybierz opcję **Parametry modułu Human Resources**.</span><span class="sxs-lookup"><span data-stu-id="e8105-117">Under **Setup**, select **Human resources parameters**.</span></span>

3. <span data-ttu-id="e8105-118">Na karcie **Ogólne** w obszarze **REKRUTACJA** przy opcji **Włącz wnioski o rekrutację** ustaw **Tak**.</span><span class="sxs-lookup"><span data-stu-id="e8105-118">On the **General** tab, under **RECRUITING**, set **Enable recruiting requests** to **Yes**.</span></span>

   ![Włącz wnioski o rekrutację](./media/hr-recruit-0-enable-requests.png)

## <a name="add-a-recruiting-request-location"></a><span data-ttu-id="e8105-120">Dodawanie lokalizacji wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="e8105-120">Add a recruiting request location</span></span>

<span data-ttu-id="e8105-121">Jeśli organizacja ma wiele lokalizacji, można je dodać, tak aby wnioskodawca mógł wybrać lokalizację, w której będzie pracowała nowa osoba.</span><span class="sxs-lookup"><span data-stu-id="e8105-121">If your organization has multiple locations, you can add them so requestors can select a location where the new recruit will be working.</span></span> <span data-ttu-id="e8105-122">Lokalizacja zostanie uwzględniona w publikacji oferty pracy.</span><span class="sxs-lookup"><span data-stu-id="e8105-122">The location will be included in the job posting.</span></span>

1. <span data-ttu-id="e8105-123">Na pasku wyszukiwania wprowadź **lokalizację wniosku o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="e8105-123">In the search bar, enter **recruiting request location**.</span></span>

2. <span data-ttu-id="e8105-124">Wybierz pozycję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e8105-124">Select **New**.</span></span>

3. <span data-ttu-id="e8105-125">W polu **Lokalizacja wniosku o rekrutację** wprowadź nazwę lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-125">In the **Recruiting request location** field, enter the location name.</span></span>

   ![Dodawanie lokalizacji wniosku o rekrutację](./media/hr-recruit-0a-add-location.png)

4. <span data-ttu-id="e8105-127">W polu **Opis** wprowadź opis lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-127">In the **Description**, enter a description for the location.</span></span>

5. <span data-ttu-id="e8105-128">W obszarze **Lokalizacja** wybierz **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="e8105-128">Under **Location**, select **Add**.</span></span> <span data-ttu-id="e8105-129">Jeśli pojawi się okno **Nowy adres**, wprowadź adres lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-129">If the **New address** popout appears, enter the address for the location.</span></span>

   ![Wprowadź adres](./media/hr-recruit-0b-address.png)

6. <span data-ttu-id="e8105-131">W obszarze **Informacje kontaktowe** wprowadź dane osoby do kontaktu w tej lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-131">Under **Contact information**, enter the information for the location's contact.</span></span>

7. <span data-ttu-id="e8105-132">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8105-132">Select **Save**.</span></span>

## <a name="add-a-recruiting-request"></a><span data-ttu-id="e8105-133">Dodawanie wniosku o rekrutację</span><span class="sxs-lookup"><span data-stu-id="e8105-133">Add a recruiting request</span></span>

<span data-ttu-id="e8105-134">Menedżerowie mogą przesyłać wnioski o rekrutację w module Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e8105-134">Managers can submit recruiting requests in Human Resources.</span></span> <span data-ttu-id="e8105-135">W przypadku korzystania z oddzielnej aplikacji do rekrutacji wykonanie tych kroków spowoduje wysłanie wniosku o rekrutację i rozpoczęcie procesu rekrutacji w tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-135">If you use a separate recruiting application, completing these steps will send a recruiting request and start the recruiting process in that application.</span></span> <span data-ttu-id="e8105-136">W przeciwnym razie procedura ta po prostu rozpocznie wewnętrzny proces rekrutacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-136">Otherwise, complete this procedure to begin the workflow for your own internal recruiting process.</span></span>

1. <span data-ttu-id="e8105-137">Wybierz opcję **Samoobsługa pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="e8105-137">Select **Employee self service**.</span></span>

2. <span data-ttu-id="e8105-138">Wybierz kartę **Mój zespół**.</span><span class="sxs-lookup"><span data-stu-id="e8105-138">Select the **My team** tab.</span></span>

3. <span data-ttu-id="e8105-139">Wybierz **Złóż wniosek o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="e8105-139">Select  **Request to recruit**.</span></span>

   ![Uruchamianie wniosku o rekrutację](./media/hr-recruit-1-request-to-recruit.png)

4. <span data-ttu-id="e8105-141">Wypełnij pola **Opis**, **Stanowisko** i **Szacowana data rozpoczęcia**.</span><span class="sxs-lookup"><span data-stu-id="e8105-141">Complete the **Description**, **Job**, and **Estimated start date** fields.</span></span>

   ![Zakończenie tworzenia wniosku o rekrutację](./media/hr-recruit-2-request-to-recruit.png)

5. <span data-ttu-id="e8105-143">Kliknij przycisk **Kontynuuj**.</span><span class="sxs-lookup"><span data-stu-id="e8105-143">Select **Continue**.</span></span> <span data-ttu-id="e8105-144">Wniosek o rekrutację na dane stanowisko zostanie utworzony.</span><span class="sxs-lookup"><span data-stu-id="e8105-144">The recruiting request for your position appears.</span></span>

6. <span data-ttu-id="e8105-145">W obszarze **Ogólne** wybierz osobę rekrutującą z listy rozwijanej **Osoba rekrutująca**, a następnie wybierz lokalizację z listy rozwijanej **Lokalizacja wniosku o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="e8105-145">Under **General**, select a recruiter from the **Recruiter** dropdown, and then select a location from the **Recruiting request location** dropdown.</span></span>

7. <span data-ttu-id="e8105-146">W obszarze **Stanowisko** zmień informacje zależnie od potrzeb, a następnie wybierz opcję **Utwórz szczegóły ze stanowiska**.</span><span class="sxs-lookup"><span data-stu-id="e8105-146">Under **Job**, change any information as needed, and then select **Create details from job**.</span></span>

   ![Utwórz szczegóły ze stanowiska](./media/hr-recruit-3-create-details-from-job.png)

   <span data-ttu-id="e8105-148">Pozostała część wniosku o rekrutację zostanie wypełniona domyślnymi informacjami dotyczącymi danego stanowiska.</span><span class="sxs-lookup"><span data-stu-id="e8105-148">The rest of the recruiting request will populate with the default information for the job you entered.</span></span>

8. <span data-ttu-id="e8105-149">W obszarze **Zewnętrzny opis** wprowadź opis stanowiska do udostępnienia poza firmą.</span><span class="sxs-lookup"><span data-stu-id="e8105-149">Under **External description**, enter an external-facing job description.</span></span>

9. <span data-ttu-id="e8105-150">W obszarze **Stanowiska** wybierz opcję **Dodaj**, a następnie wybierz stanowisko dla danego wniosku o rekrutację.</span><span class="sxs-lookup"><span data-stu-id="e8105-150">Under **Positions**, select **Add**, and then select a position for this recruiting request.</span></span>

   ![Dodawanie stanowiska](./media/hr-recruit-4-select-position.png)

10. <span data-ttu-id="e8105-152">W obszarze **Umiejętności** wybierz opcję **Dodaj**, a następnie wybierz umiejętność.</span><span class="sxs-lookup"><span data-stu-id="e8105-152">Under **Skills**, select **Add**, and then select a skill.</span></span>

11. <span data-ttu-id="e8105-153">W obszarze **Wymagane wykształcenie** wybierz opcję **Dodaj**, a następnie wybierz wartości z list rozwijanych **Wykształcenie** i **Poziom wykształcenia**.</span><span class="sxs-lookup"><span data-stu-id="e8105-153">Under **Educational requirements**, select **Add**, and then select values from the **Education** and **Level of education** dropdowns.</span></span>

   ![Dodawanie wymagań dotyczących wykształcenia](./media/hr-recruit-5-select-educational-requirements.png)

12. <span data-ttu-id="e8105-155">W obszarze **Komentarz** dodaj opcjonalne uwagi.</span><span class="sxs-lookup"><span data-stu-id="e8105-155">Under **Comment**, add comments as necessary.</span></span>

13. <span data-ttu-id="e8105-156">W obszarze **Wynagrodzenie** wybierz poziom z listy rozwijanej **Poziom**, a następnie odpowiednio dostosuj **Próg niski**, **Punkt kontrolny** i **Próg wysoki**.</span><span class="sxs-lookup"><span data-stu-id="e8105-156">Under **Compensation**, select a level from the **Level** dropdown, and then adjust **Low threshold**, **Control point**, and **High threshold** as necessary.</span></span>

14. <span data-ttu-id="e8105-157">Gdy wniosek o rekrutację będzie gotowy i można rozpocząć proces rekrutacji, wybierz opcję **Uaktywnij** na pasku menu.</span><span class="sxs-lookup"><span data-stu-id="e8105-157">When your recruiting request is complete and you're ready to start the recruiting process, select **Activate** in the menu bar.</span></span>

   ![Aktywacja wniosku o rekrutację](./media/hr-recruit-6-activate-recruit-request.png)

15. <span data-ttu-id="e8105-159">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8105-159">Select **Save**.</span></span>

## <a name="view-and-edit-your-recruiting-requests"></a><span data-ttu-id="e8105-160">Wyświetlanie i edytowanie wniosków o rekrutację</span><span class="sxs-lookup"><span data-stu-id="e8105-160">View and edit your recruiting requests</span></span>

<span data-ttu-id="e8105-161">Jeśli jesteś menedżerem i chcesz wyświetlić swoje własne wnioski:</span><span class="sxs-lookup"><span data-stu-id="e8105-161">If you're a manager and want to view your own requests:</span></span>

1. <span data-ttu-id="e8105-162">Wybierz opcję **Samoobsługa pracownika etatowego**.</span><span class="sxs-lookup"><span data-stu-id="e8105-162">Select **Employee self service**.</span></span>

2. <span data-ttu-id="e8105-163">Wybierz kartę **Mój zespół**.</span><span class="sxs-lookup"><span data-stu-id="e8105-163">Select the **My team** tab.</span></span>

3. <span data-ttu-id="e8105-164">W obszarze **Informacje dotyczące mojego zespołu** wybierz kartę **Wnioski o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="e8105-164">Under **My team information**, select the **Recruiting requests** tab.</span></span>

   ![Wybierz kartę Wnioski o rekrutację](./media/hr-recruit-7-recruiting-requests.png)

4. <span data-ttu-id="e8105-166">Aby wyświetlić lub edytować wniosek o rekrutację, należy wybrać go z tabeli.</span><span class="sxs-lookup"><span data-stu-id="e8105-166">To view or edit a recruiting request, select it in the grid.</span></span>

<span data-ttu-id="e8105-167">Jeśli jesteś pracownikiem działu kadr i chcesz przejrzeć wszystkie wnioski o rekrutację:</span><span class="sxs-lookup"><span data-stu-id="e8105-167">If you're an HR pro and want to view all recruiting requests:</span></span>

1. <span data-ttu-id="e8105-168">Wybierz **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="e8105-168">Select **Personnel management**.</span></span>

2. <span data-ttu-id="e8105-169">Wybierz **Wnioski o rekrutację**.</span><span class="sxs-lookup"><span data-stu-id="e8105-169">Select **Recruiting requests**.</span></span>

   ![Wyświetlanie wniosków o rekrutację na stronie Zarządzanie personelem](./media/hr-recruit-8-recruiting-requests-personnel-management.png)

3. <span data-ttu-id="e8105-171">Aby wyświetlić lub edytować wniosek o rekrutację, należy wybrać go z tabeli.</span><span class="sxs-lookup"><span data-stu-id="e8105-171">To view or edit a recruiting request, select it in the grid.</span></span>

## <a name="add-or-edit-a-candidate-profile"></a><span data-ttu-id="e8105-172">Dodawanie lub edytowanie profilu kandydata</span><span class="sxs-lookup"><span data-stu-id="e8105-172">Add or edit a candidate profile</span></span>

<span data-ttu-id="e8105-173">Jeśli zarządzanie wnioskami o rekrutację zostało zintegrowane z inną aplikacją, to wnioski są przekazywane do tej aplikacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-173">If your organization has integrated with another application to manage recruiting requests, recruiting requests are forwarded to that application.</span></span> <span data-ttu-id="e8105-174">Następnie aplikacja do rekrutacji wysyła informacje o kandydatach do modułu Human Resources.</span><span class="sxs-lookup"><span data-stu-id="e8105-174">The recruiting application then sends candidate information back to Human Resources.</span></span> <span data-ttu-id="e8105-175">W przeciwnym razie możesz postępować zgodnie z wewnętrznym procesem rekrutacji oraz wprowadzać dane kandydatów ręcznie.</span><span class="sxs-lookup"><span data-stu-id="e8105-175">Otherwise, you can follow your own internal recruiting processes and enter candidate information manually.</span></span>

1. <span data-ttu-id="e8105-176">Wybierz **Zarządzanie personelem**.</span><span class="sxs-lookup"><span data-stu-id="e8105-176">Select **Personnel management**.</span></span>

2. <span data-ttu-id="e8105-177">Wybierz **Łącza**.</span><span class="sxs-lookup"><span data-stu-id="e8105-177">Select **Links**.</span></span>

3. <span data-ttu-id="e8105-178">W obszarze **Rekrutacja** wybierz opcję **Kandydaci**.</span><span class="sxs-lookup"><span data-stu-id="e8105-178">Under **Recruiting**, select **Candidates**.</span></span>

   ![Wyświetlanie kandydatów](./media/hr-recruit-9-candidates.png)

4. <span data-ttu-id="e8105-180">Aby dodać kandydata, wybierz opcję **Nowy**.</span><span class="sxs-lookup"><span data-stu-id="e8105-180">To add a candidate, select **New**.</span></span> <span data-ttu-id="e8105-181">Aby edytować dane istniejącego kandydata, wybierz go z listy i wybierz opcję **Edytuj**.</span><span class="sxs-lookup"><span data-stu-id="e8105-181">To edit an existing candidate, select the candidate from the list and then select **Edit**.</span></span> <span data-ttu-id="e8105-182">Zostanie wyświetlony profil kandydata.</span><span class="sxs-lookup"><span data-stu-id="e8105-182">The candidate profile appears.</span></span>

5. <span data-ttu-id="e8105-183">W obszarze **Podsumowanie dotyczące kandydata** wprowadź lub zmień odpowiednie dane kandydatów.</span><span class="sxs-lookup"><span data-stu-id="e8105-183">Under **Candidate summary**, enter or edit the candidate information as necessary.</span></span>

6. <span data-ttu-id="e8105-184">W obszarze **Wniosek o rekrutację** wybierz wniosek o rekrutację, z którym ma być połączony kandydat.</span><span class="sxs-lookup"><span data-stu-id="e8105-184">Under **Recruiting request**, select a recruiting request to link the candidate to.</span></span> <span data-ttu-id="e8105-185">Następnie wypełnij pola **Szacunkowa data rozpoczęcia**, **Menedżer zatrudniający**, **Stanowisko** i **Opis**.</span><span class="sxs-lookup"><span data-stu-id="e8105-185">Then complete the **Estimated start date**, **Hiring manager**, **Position**, and **Description fields** as appropriate.</span></span>

   ![Łączenie z wnioskiem o rekrutację](./media/hr-recruit-10-link-to-recruiting-request.png)

7. <span data-ttu-id="e8105-187">Uzupełnij wszystkie informacje w następujących obszarach, które chcesz uwzględnić w rekordzie kandydata:</span><span class="sxs-lookup"><span data-stu-id="e8105-187">Complete all the information in the following areas that you want to include in the candidate's record:</span></span>
   - <span data-ttu-id="e8105-188">**Komentarze**</span><span class="sxs-lookup"><span data-stu-id="e8105-188">**Comments**</span></span>
   - <span data-ttu-id="e8105-189">**Doświadczenie zawodowe**</span><span class="sxs-lookup"><span data-stu-id="e8105-189">**Professional experience**</span></span>
   - <span data-ttu-id="e8105-190">**Informacje o kontakcie**</span><span class="sxs-lookup"><span data-stu-id="e8105-190">**Contact information**</span></span>
   - <span data-ttu-id="e8105-191">**Wykształcenie**</span><span class="sxs-lookup"><span data-stu-id="e8105-191">**Education**</span></span>
   - <span data-ttu-id="e8105-192">**Umiejętności**</span><span class="sxs-lookup"><span data-stu-id="e8105-192">**Skills**</span></span>
   - <span data-ttu-id="e8105-193">**Certyfikaty**</span><span class="sxs-lookup"><span data-stu-id="e8105-193">**Certificates**</span></span>
   - <span data-ttu-id="e8105-194">**Kontrole**</span><span class="sxs-lookup"><span data-stu-id="e8105-194">**Screenings**</span></span>

8. <span data-ttu-id="e8105-195">Wybierz opcję **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="e8105-195">Select **Save**.</span></span>

## <a name="hire-a-candidate"></a><span data-ttu-id="e8105-196">Zatrudnianie kandydata</span><span class="sxs-lookup"><span data-stu-id="e8105-196">Hire a candidate</span></span>

<span data-ttu-id="e8105-197">Gdy firma jest gotowa do zatrudnienia kandydata, wykonaj poniższe kroki, aby zmienić kandydata w pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="e8105-197">When you're ready to hire a candidate, follow this procedure to transition the candidate to an employee.</span></span>

1. <span data-ttu-id="e8105-198">W formularzu kandydata wybierz **Zatrudnij**.</span><span class="sxs-lookup"><span data-stu-id="e8105-198">On the candidate form, select **Hire**.</span></span>

   ![Zatrudnianie kandydata](./media/hr-recruit-11-hire.png)

2. <span data-ttu-id="e8105-200">Wypełnij wszystkie pola w formularzu **Zatrudnij nowego pracownika** w obszarze **Szczegóły**.</span><span class="sxs-lookup"><span data-stu-id="e8105-200">On the **Hire new worker** form, under **Details**, complete all the fields.</span></span>

   ![Wprowadzanie danych dotyczących zatrudnianej osoby](./media/hr-recruit-12-hire-new-worker.png)

3. <span data-ttu-id="e8105-202">Sprawdź dane w obszarze **Szczegóły dotyczące stanowiska** i zmodyfikuj je w razie potrzeby.</span><span class="sxs-lookup"><span data-stu-id="e8105-202">Under **Position details**, verify and change information as necessary.</span></span>

4. <span data-ttu-id="e8105-203">W obszarze **Listy kontrolne wdrażania do pracy** wybierz odpowiednie listy kontrolne dla danego pracownika.</span><span class="sxs-lookup"><span data-stu-id="e8105-203">Under **Onboarding checklists**, select the relevant onboarding checklists for this employee.</span></span>

5. <span data-ttu-id="e8105-204">Wybierz **Kontynuuj**, aby utworzyć rekord pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="e8105-204">Select **Continue** to create the employee record.</span></span>

   >[!NOTE]
   ><span data-ttu-id="e8105-205">W zależności od procedur w organizacji mogą być wymagane dodatkowe kroki zatwierdzania rekordu kandydata, zanim stanie się on rekordem pracownika etatowego.</span><span class="sxs-lookup"><span data-stu-id="e8105-205">Depending on your organization's workflows, the candidate record may go through additional approval steps before becoming an employee record.</span></span>

## <a name="decide-not-to-hire-a-candidate"></a><span data-ttu-id="e8105-206">Decyzja o niezatrudnianiu kandydata</span><span class="sxs-lookup"><span data-stu-id="e8105-206">Decide not to hire a candidate</span></span>

<span data-ttu-id="e8105-207">W przypadku decyzji o niezatrudnianiu kandydata postępuj zgodnie z poniższą instrukcją, aby wykluczyć go z procesu weryfikacji.</span><span class="sxs-lookup"><span data-stu-id="e8105-207">If you decide not to hire a candidate, follow this procedure to remove them from the vetting process.</span></span> 

1. <span data-ttu-id="e8105-208">W formularzu kandydata wybierz **Nie zatrudniaj**.</span><span class="sxs-lookup"><span data-stu-id="e8105-208">On the candidate form, select **Do not hire**.</span></span>

   ![Niezatrudnianie kandydata](./media/hr-recruit-13-do-not-hire.png)

2. <span data-ttu-id="e8105-210">Wybierz **Kod przyczyny** i dodaj swoje uwagi.</span><span class="sxs-lookup"><span data-stu-id="e8105-210">Select a **Reason code** and include any comments.</span></span>

3. <span data-ttu-id="e8105-211">Kliknij przycisk **OK**.</span><span class="sxs-lookup"><span data-stu-id="e8105-211">Select **OK**.</span></span>

## <a name="dismiss-a-candidate"></a><span data-ttu-id="e8105-212">Odrzucanie kandydata</span><span class="sxs-lookup"><span data-stu-id="e8105-212">Dismiss a candidate</span></span>

<span data-ttu-id="e8105-213">Jeśli zajdzie potrzeba, można odrzucić kandydata po jego zatrudnieniu.</span><span class="sxs-lookup"><span data-stu-id="e8105-213">If needed, you can dismiss a candidate after hiring them.</span></span> <span data-ttu-id="e8105-214">Na przykład kandydat może wycofać swoją ofertę lub nie stawić się w pracy pierwszego dnia.</span><span class="sxs-lookup"><span data-stu-id="e8105-214">For example, a candidate might reject your offer or not show up on their first day.</span></span>

- <span data-ttu-id="e8105-215">W formularzu kandydata wybierz **Odrzuć kandydata**.</span><span class="sxs-lookup"><span data-stu-id="e8105-215">On the candidate form, select **Dismiss candidate**.</span></span>

  ![Odrzuć kandydata](./media/hr-recruit-14-dismiss-candidate.png)

## <a name="see-also"></a><span data-ttu-id="e8105-217">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="e8105-217">See also</span></span>

[<span data-ttu-id="e8105-218">Konfigurowanie jednostek wirtualnych usługi Common Data Service</span><span class="sxs-lookup"><span data-stu-id="e8105-218">Configure Common Data Service virtual entities</span></span>](hr-admin-integration-common-data-service-virtual-entities.md)<br>
[<span data-ttu-id="e8105-219">Organizowanie pracowników</span><span class="sxs-lookup"><span data-stu-id="e8105-219">Organize your workforce</span></span>](hr-personnel-departments-jobs-positions.md)<br>
[<span data-ttu-id="e8105-220">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="e8105-220">Set up the components of a job</span></span>](hr-personnel-jobs.md)