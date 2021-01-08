---
title: Eksportowanie danych z Attract i Onboard
description: Eksportowanie danych z Dynamics 365 Talent - Attract i Onboard.
author: andreabichsel
manager: AnnBe
ms.date: 01/14/2020
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
ms.search.validFrom: 2020-01-14
ms.dyn365.ops.version: Talent October 2019 update
ms.openlocfilehash: eb97a16c15476c2f34ec581a32a677fa6fee8739
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4462178"
---
# <a name="export-data-from-attract-and-onboard"></a><span data-ttu-id="1e90b-103">Eksportowanie danych z Attract i Onboard</span><span class="sxs-lookup"><span data-stu-id="1e90b-103">Export data from Attract and Onboard</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="1e90b-104">Zgodnie z informacjami w [Wycodywanie aplikacji Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), wycofujemy aplikacje Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard  1 lutego 2022.</span><span class="sxs-lookup"><span data-stu-id="1e90b-104">As announced in [Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps), we're retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard on February 1, 2022.</span></span> <span data-ttu-id="1e90b-105">Aby ułatwić migrację do innego produktu, w obu tych aplikacjach są dostępne funkcje eksportu danych.</span><span class="sxs-lookup"><span data-stu-id="1e90b-105">To help with your migration to another product, both apps now provide data export capabilities.</span></span>

## <a name="export-data-from-attract"></a><span data-ttu-id="1e90b-106">Eksportowanie danych z Attract</span><span class="sxs-lookup"><span data-stu-id="1e90b-106">Export data from Attract</span></span>

<span data-ttu-id="1e90b-107">Można eksportować dane bez ograniczania dostępu do środowiska.</span><span class="sxs-lookup"><span data-stu-id="1e90b-107">You can export your data without restricting access to your environment.</span></span> <span data-ttu-id="1e90b-108">Może to być przydatne w celach testowych lub do zrozumienia struktury danych.</span><span class="sxs-lookup"><span data-stu-id="1e90b-108">You might want to do this for testing purposes or to understand our data structure.</span></span> <span data-ttu-id="1e90b-109">Gdy wszystko będzie gotowe do migracji, należy ograniczyć dostęp do środowiska Attract, korzystając z instrukcji opisanej po tej procedurze.</span><span class="sxs-lookup"><span data-stu-id="1e90b-109">When you're ready to migrate, restrict access to your Attract environment using the instructions after this procedure.</span></span> <span data-ttu-id="1e90b-110">Należy pamiętać o ponownym wyeksportowaniu danych.</span><span class="sxs-lookup"><span data-stu-id="1e90b-110">Be sure to export your data again.</span></span> 

1. <span data-ttu-id="1e90b-111">Przejdź do [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="1e90b-111">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="1e90b-112">W obszarze **Eksportowanie danych** wybierz opcję **Żądaj eksportu danych**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-112">Under **Data export**, select **Request a data export**.</span></span>

   ![[<span data-ttu-id="1e90b-113">Zażądaj eksportu danych z Attract</span><span class="sxs-lookup"><span data-stu-id="1e90b-113">Request a data export from Attract</span></span>](./media/attract-onboard-export-data-attract-request.png)](./media/attract-onboard-export-data-attract-request.png)

3. <span data-ttu-id="1e90b-114">Po wyświetleniu okna komunikatu, **Twoje żądanie jest przetwarzane** wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-114">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="1e90b-115">Eksport danych może potrwać do 20 minut, w zależności od rozmiaru eksportu.</span><span class="sxs-lookup"><span data-stu-id="1e90b-115">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="1e90b-116">Po zakończeniu eksportu wybierz znajdujący się obok przycisk **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-116">When your export completes, select the **Download** button next to it.</span></span> 

   >[!NOTE]
   ><span data-ttu-id="1e90b-117">Wszystkie operacje eksportu danych są dostępne przez siedem dni, w którym łącze **Pobierz** wygasa.</span><span class="sxs-lookup"><span data-stu-id="1e90b-117">All data exports are available for seven days, at which point the **Download** link expires.</span></span></br>
   
<span data-ttu-id="1e90b-118">Pobieranie zawiera plik .zip z danymi Attract, w tym następujące foldery:</span><span class="sxs-lookup"><span data-stu-id="1e90b-118">The download contains a .zip file with your Attract data, including the following folders:</span></span>

| <span data-ttu-id="1e90b-119">Nazwa folderu</span><span class="sxs-lookup"><span data-stu-id="1e90b-119">Folder name</span></span> | <span data-ttu-id="1e90b-120">Opis</span><span class="sxs-lookup"><span data-stu-id="1e90b-120">Description</span></span> |
| --- | --- |
| <span data-ttu-id="1e90b-121">Ustawienia administratora</span><span class="sxs-lookup"><span data-stu-id="1e90b-121">Admin settings</span></span> | <span data-ttu-id="1e90b-122">Konfiguracja centrum administracyjnego Attract.</span><span class="sxs-lookup"><span data-stu-id="1e90b-122">Attract admin center configurations.</span></span> |
| <span data-ttu-id="1e90b-123">Kandydaci</span><span class="sxs-lookup"><span data-stu-id="1e90b-123">Candidates</span></span> | <span data-ttu-id="1e90b-124">Wszyscy kandydaci, którzy zostali dodani do zadań lub pul talentów.</span><span class="sxs-lookup"><span data-stu-id="1e90b-124">All candidates that were added to jobs or talent pools.</span></span> |
| <span data-ttu-id="1e90b-125">Szablony wiadomości e-mail</span><span class="sxs-lookup"><span data-stu-id="1e90b-125">Email templates</span></span> | <span data-ttu-id="1e90b-126">Wszystkie szablony wiadomości e-mail skonfigurowane dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="1e90b-126">All email templates that were configured for the environment.</span></span> |
| <span data-ttu-id="1e90b-127">Szablony pakietów ofert pracy</span><span class="sxs-lookup"><span data-stu-id="1e90b-127">Job offer package templates</span></span> | <span data-ttu-id="1e90b-128">Wszystkie utworzone szablony pakietu ofert pracy oraz skojarzone z nimi konfiguracje.</span><span class="sxs-lookup"><span data-stu-id="1e90b-128">All job offer package templates that were created, plus their associated configurations.</span></span> |
| <span data-ttu-id="1e90b-129">Zestawy reguł oferty pracy</span><span class="sxs-lookup"><span data-stu-id="1e90b-129">Job offer rule sets</span></span> |  <span data-ttu-id="1e90b-130">Wszystkie pliki zestawów reguł przekazane dla zarządzania ofertami.</span><span class="sxs-lookup"><span data-stu-id="1e90b-130">All rule set files that were uploaded for offer management.</span></span> |
| <span data-ttu-id="1e90b-131">Szablony ofert pracy</span><span class="sxs-lookup"><span data-stu-id="1e90b-131">Job offer templates</span></span> | <span data-ttu-id="1e90b-132">Wszystkie szablony dokumentów ofert pracy utworzone dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="1e90b-132">All job offer document templates created for the environment.</span></span> |
| <span data-ttu-id="1e90b-133">Wakaty</span><span class="sxs-lookup"><span data-stu-id="1e90b-133">Job openings</span></span> | <span data-ttu-id="1e90b-134">Wszystkie utworzone zadania.</span><span class="sxs-lookup"><span data-stu-id="1e90b-134">All created jobs.</span></span> <span data-ttu-id="1e90b-135">Usunięte zadania nie są eksportowane.</span><span class="sxs-lookup"><span data-stu-id="1e90b-135">Deleted jobs aren't exported.</span></span> <span data-ttu-id="1e90b-136">Podfoldery zawierają aplikacje kandydatów, z podfolderami służącymi do umieszczania załączników w aplikacjach kandydatów i oferują pakiety ofert, gdzie ma to zastosowanie.</span><span class="sxs-lookup"><span data-stu-id="1e90b-136">The sub-folders contain candidate applications, with sub-folders for candidate application attachments and offer packages, where applicable.</span></span> |
| <span data-ttu-id="1e90b-137">Szablony wakatów</span><span class="sxs-lookup"><span data-stu-id="1e90b-137">Job opening templates</span></span> | <span data-ttu-id="1e90b-138">Szablony procesu zadania skonfigurowane dla środowiska.</span><span class="sxs-lookup"><span data-stu-id="1e90b-138">Job process templates that were configured in the environment.</span></span> |
| <span data-ttu-id="1e90b-139">Pule umiejętności i kandydatów</span><span class="sxs-lookup"><span data-stu-id="1e90b-139">Talent pools</span></span> | <span data-ttu-id="1e90b-140">Wszystkie utworzone pule talentów, ich listy współautorów oraz listy kandydatów dla pul talentów.</span><span class="sxs-lookup"><span data-stu-id="1e90b-140">All created talent pools, their contributors lists, and the candidates lists for the talent pools.</span></span> |
| <span data-ttu-id="1e90b-141">Pracownicy</span><span class="sxs-lookup"><span data-stu-id="1e90b-141">Workers</span></span> | <span data-ttu-id="1e90b-142">Lista wszystkich pracowników, którzy są obecni w środowisku, oraz ich role.</span><span class="sxs-lookup"><span data-stu-id="1e90b-142">List of all the workers who are present in the environment, plus their roles.</span></span> |
| <span data-ttu-id="1e90b-143">(folder główny)</span><span class="sxs-lookup"><span data-stu-id="1e90b-143">(root folder)</span></span> | <span data-ttu-id="1e90b-144">Plik schematu JSON opisujący pola struktury danych.</span><span class="sxs-lookup"><span data-stu-id="1e90b-144">A JSON schema file that describes the data structure fields.</span></span> |

### <a name="restrict-access-to-attract"></a><span data-ttu-id="1e90b-145">Ogranicz dostęp do Attract</span><span class="sxs-lookup"><span data-stu-id="1e90b-145">Restrict access to Attract</span></span>

<span data-ttu-id="1e90b-146">Po przygotowaniu się do migracji można ograniczyć dostęp innych niż administratorzy do środowiska Attract i eksportować dane.</span><span class="sxs-lookup"><span data-stu-id="1e90b-146">When you're ready to migrate, restrict non-admins from accessing your Attract environment and export your data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="1e90b-147">Ograniczenie dostępu do środowiska Attract jest trwałe i nie można go cofnąć.</span><span class="sxs-lookup"><span data-stu-id="1e90b-147">Restricting access to your Attract environment is permanent and can't be undone.</span></span> <span data-ttu-id="1e90b-148">Jeśli chcesz, aby użytkownicy inni niż administratorzy mogli nadal uzyskiwać dostęp do środowiska, pomiń ten krok.</span><span class="sxs-lookup"><span data-stu-id="1e90b-148">If you want non-admin users to continue accessing your environment, skip this step.</span></span>

1. <span data-ttu-id="1e90b-149">Przejdź do [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span><span class="sxs-lookup"><span data-stu-id="1e90b-149">Go to [https://aka.ms/AttractDataExport](https://aka.ms/AttractDataExport).</span></span>

2. <span data-ttu-id="1e90b-150">W celu ograniczenia dostępu do środowiska przyciągania w systemie innym niż administratorzy, w obszarze **Ogranicz dostęp do tej aplikacji** wybierz pozycję **Ogranicz dostęp teraz**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-150">To restrict non-admins from accessing your Attract environment, under **Restrict access to this app**, select **Restrict access now**.</span></span> <span data-ttu-id="1e90b-151">Ograniczenie dostępu powoduje także wykonuje wyksięgowanie wszystkich aktywnych zadań, które zostały zaksięgowane.</span><span class="sxs-lookup"><span data-stu-id="1e90b-151">Restricting access also unposts any active jobs that have been posted.</span></span>

   ![[<span data-ttu-id="1e90b-152">Ogranicz dostęp dla osób innych niż administrator do Attract</span><span class="sxs-lookup"><span data-stu-id="1e90b-152">Restrict non-admin access to Attract</span></span>](./media/attract-onboard-export-data-attract-restrict-access.png)](./media/attract-onboard-export-data-attract-restrict-access.png)

3. <span data-ttu-id="1e90b-153">Po wyświetleniu ostrzeżenia jest **To stała zmiana**, zaznacz opcję **Ogranicz dostęp**, aby trwale ograniczyć liczbę użytkowników niebędących administratorami w tym środowisku.</span><span class="sxs-lookup"><span data-stu-id="1e90b-153">When you see the warning **This is a permanent change**, select **Restrict access** to permanently restrict non-admin users from this environment.</span></span> <span data-ttu-id="1e90b-154">Jeśli nie masz gotowości do wykonania tego kroku, wybierz przycisk **Anuluj**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-154">If you're not ready to complete this step, select **Cancel**.</span></span>

   ![[<span data-ttu-id="1e90b-155">Ostrzeżenie, że ograniczenie dostępu jest stałą zmianą</span><span class="sxs-lookup"><span data-stu-id="1e90b-155">Warning that restricting access is a permanent change</span></span>](./media/attract-onboard-export-data-attract-warning.png)](./media/attract-onboard-export-data-attract-warning.png)

   >[!NOTE]
   ><span data-ttu-id="1e90b-156">Administratorzy mogą nadal uzyskiwać dostęp do stron eksport danych i raportów o osobach po ograniczeniu dostępu do środowiska Attract.</span><span class="sxs-lookup"><span data-stu-id="1e90b-156">Admins can continue to access the data export and person report pages after you restrict access to the Attract environment.</span></span>

## <a name="export-data-from-onboard"></a><span data-ttu-id="1e90b-157">Eksportowanie danych z rozwiązania Onboard</span><span class="sxs-lookup"><span data-stu-id="1e90b-157">Export data from Onboard</span></span>

<span data-ttu-id="1e90b-158">Gdy wszystko będzie gotowe, można pobrać szablony, przewodniki i dane kandydatów z systemu na Onboard.</span><span class="sxs-lookup"><span data-stu-id="1e90b-158">When you're ready, you can download templates, guides, and candidate data from Onboard.</span></span>

1. <span data-ttu-id="1e90b-159">Przejdź do [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span><span class="sxs-lookup"><span data-stu-id="1e90b-159">Go to [https://aka.ms/OnboardDataExport](https://aka.ms/OnboardDataExport).</span></span>

2. <span data-ttu-id="1e90b-160">W obszarze **Eksportowanie danych** wybierz opcję **Żądaj eksportu danych**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-160">Under **Data export**, select **Request a data export**.</span></span> 

   ![[<span data-ttu-id="1e90b-161">Zażądaj eksportu danych z Onboard</span><span class="sxs-lookup"><span data-stu-id="1e90b-161">Request a data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-request.png)](./media/attract-onboard-export-data-onboard-request.png)

3. <span data-ttu-id="1e90b-162">Po wyświetleniu okna komunikatu, **Twoje żądanie jest przetwarzane** wybierz **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-162">When the **Your request is being processed** message box appears, select **OK**.</span></span> <span data-ttu-id="1e90b-163">Eksport danych może potrwać do 20 minut, w zależności od rozmiaru eksportu.</span><span class="sxs-lookup"><span data-stu-id="1e90b-163">The data export can take up to 20 minutes, depending on the size of your export.</span></span>

4. <span data-ttu-id="1e90b-164">Po zakończeniu eksportu wybierz znajdujący się obok przycisk **Pobierz**.</span><span class="sxs-lookup"><span data-stu-id="1e90b-164">When your export completes, select the **Download** button next to it.</span></span> 

   ![[<span data-ttu-id="1e90b-165">Pobieranie danych eksportowanych z rozwiązania Onboard</span><span class="sxs-lookup"><span data-stu-id="1e90b-165">Download data export from Onboard</span></span>](./media/attract-onboard-export-data-onboard-download.png)](./media/attract-onboard-export-data-onboard-download.png)

   >[!NOTE]
   ><span data-ttu-id="1e90b-166">Eksport danych jest dostępny przez siedem dni.</span><span class="sxs-lookup"><span data-stu-id="1e90b-166">Your data export is available for seven days.</span></span> <span data-ttu-id="1e90b-167">Po siedmiu dniach łącze **Pobierz** wygaśnie i trzeba będzie zażądać nowego eksportu, jeśli trzeba będzie ponownie pobrać dane.</span><span class="sxs-lookup"><span data-stu-id="1e90b-167">After seven days, the **Download** link expires, and you must request a new export if you need to download your data again.</span></span> <span data-ttu-id="1e90b-168">Po uruchomieniu nowego eksportu danych wszelkie istniejące pliki do pobrania wygasną po pomyślnym zakończeniu nowego eksportu.</span><span class="sxs-lookup"><span data-stu-id="1e90b-168">When you start a new data export, any existing downloads will expire after the new export succeeds.</span></span>

<span data-ttu-id="1e90b-169">Pobierany plik jest plikiem .zip zawierający:</span><span class="sxs-lookup"><span data-stu-id="1e90b-169">The download is a .zip file that contains:</span></span>

- <span data-ttu-id="1e90b-170">Folder **Szablony**, który zawiera szablony Onboard w formacie dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="1e90b-170">A **Templates** folder that contains your Onboard templates in Word document format.</span></span>

- <span data-ttu-id="1e90b-171">Folder **Guides**, który zawiera przewodniki Onboard w formacie dokumentu programu Word.</span><span class="sxs-lookup"><span data-stu-id="1e90b-171">A **Guides** folder that contains your Onboard guides in Word document format.</span></span>

## <a name="see-also"></a><span data-ttu-id="1e90b-172">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="1e90b-172">See also</span></span>

[<span data-ttu-id="1e90b-173">Wycofywanie aplikacji Dynamics 365 Talent: Attract i Dynamics 365 Talent: Onboard</span><span class="sxs-lookup"><span data-stu-id="1e90b-173">Retiring Dynamics 365 Talent: Attract and Dynamics 365 Talent: Onboard Apps</span></span>](https://community.dynamics.com/365/talent/b/dynamics365fortalent/posts/retiring-dynamics-365-talent-attract-and-onboard-apps)