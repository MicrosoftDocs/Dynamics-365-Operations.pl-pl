---
title: Konfigurowanie integracji listy płac między rozwiązaniami Talent i Dayforce
description: W tym temacie wyjaśniono sposób konfigurowania integracji między programami Microsoft Dynamics 365 Talent i Ceridian Dayforce, dzięki czemu można przetwarzać sekcję płatności.
author: andreabichsel
manager: AnnBe
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations, Talent
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: ec1d14cb14ab709dfc1bead4be0785904efcce4e
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/30/2019
ms.locfileid: "2251046"
---
# <a name="configure-the-payroll-integration-between-talent-and-dayforce"></a><span data-ttu-id="ebf3f-103">Konfigurowanie integracji listy płac między rozwiązaniami Talent i Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-103">Configure the payroll integration between Talent and Dayforce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="ebf3f-104">Integracja między programami Microsoft Dynamics 365 Talent i Ceridian Dayforce opiera się na kilku krokach konfiguracji, które opisano w tym temacie.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-104">The integration between Microsoft Dynamics 365 Talent and Ceridian Dayforce relies on several configuration steps that are described in this topic.</span></span> <span data-ttu-id="ebf3f-105">Aby można było przetwarzać sesję płatności, należy skonfigurować integrację w rozwiązaniach Talent i Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-105">You must configure the integration in both Talent and Dayforce before you can process a pay run.</span></span>

<span data-ttu-id="ebf3f-106">Jeśli korzystasz z usługi takiej jak Dayforce do realizowania sesji płatności, należy włączyć integrację w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-106">When you use a service such as Dayforce to complete pay runs, you must enable the integration in Talent.</span></span> <span data-ttu-id="ebf3f-107">Integracja wymaga określonych danych z programu Talent.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-107">The integration requires specific data from Talent.</span></span> <span data-ttu-id="ebf3f-108">W związku z tym należy sprawdzić, czy dane mapowane do systemu Dayforce są skonfigurowano w aplikacji Talent w sposób zapewniający obsługę integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-108">Therefore, you must verify that data that is mapped to Dayforce is configured in Talent in a manner that supports the integration.</span></span> <span data-ttu-id="ebf3f-109">Integracja wykorzystuje następujące ogólne kategorie danych:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-109">The integration uses the following broad categories of data:</span></span>

- <span data-ttu-id="ebf3f-110">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-110">Human resources data</span></span>
- <span data-ttu-id="ebf3f-111">Dane o wynagrodzeniach</span><span class="sxs-lookup"><span data-stu-id="ebf3f-111">Compensation data</span></span>
- <span data-ttu-id="ebf3f-112">Dane listy płac, takie jak cykle kalkulacji płac, okresy kalkulacji płac i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-112">Payroll data, such as pay cycles, pay periods, and earning codes</span></span>
- <span data-ttu-id="ebf3f-113">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="ebf3f-113">Worker data</span></span>

<span data-ttu-id="ebf3f-114">W tym temacie opisano czynności, które należy wykonać, aby włączyć integrację.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-114">This topic describes the steps that you must follow to enable the integration.</span></span> <span data-ttu-id="ebf3f-115">Objaśniono tu także typy danych i szczegóły konfiguracji, których wymaga integracja.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-115">It also explains the types of data and the configuration details that the integration requires.</span></span>

## <a name="enable-the-integration"></a><span data-ttu-id="ebf3f-116">Włączanie integracji</span><span class="sxs-lookup"><span data-stu-id="ebf3f-116">Enable the integration</span></span>

<span data-ttu-id="ebf3f-117">W aplikacji Talent należy włączyć funkcję integracji i wprowadzić informacje konfiguracyjne w celu nawiązania połączenia z systemem Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-117">In Talent, you must turn on the integration and enter the configuration information to connect to Dayforce.</span></span> <span data-ttu-id="ebf3f-118">Jeśli chcesz, aby generowane transakcje księgi głównej były importowane do usługi Microsoft Dynamics 365 Finance, należy także skonfigurować konto magazynu w usłudze Microsoft Azure oraz wprowadzić ciąg połączenia z usługą Azure Storage w aplikacji Finance.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-118">If you want the general ledger transaction that is produced to be imported into Microsoft Dynamics 365 Finance, you must also set up a Microsoft Azure storage account and enter the Azure Storage connection string in Finance.</span></span>

<span data-ttu-id="ebf3f-119">Aby włączyć integrację w aplikacji Talent, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-119">To turn on the integration in Talent, follow these steps.</span></span>

1. <span data-ttu-id="ebf3f-120">Na stronie **Administrowanie systemem** wybierz opcję **Konfiguracja integracji**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-120">On the **System administration** page, select **Integration configuration**.</span></span>
2. <span data-ttu-id="ebf3f-121">Wprowadź punkt końcowy objęty bezpiecznym protokołem FTP (File Transfer Protocol) i ścieżkę do folderu objętego bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-121">Enter the secure File Transfer Protocol (FTP) endpoint and the secure FTP folder path.</span></span>
3. <span data-ttu-id="ebf3f-122">Wprowadź nazwę użytkownika i hasło użytkownika, który będzie uzyskiwał dostęp do punktu końcowego i ścieżki folderu objętych bezpiecznym protokołem FTP.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-122">Enter the user name and password of the user who will access the secure FTP endpoint and folder path.</span></span>
4. <span data-ttu-id="ebf3f-123">Przetestuj połączenie, a w opcji **Włącz integrację listy płac** ustaw wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-123">Test the connection, as required, and set the **Enable payroll integration** option to **Yes**.</span></span>

<span data-ttu-id="ebf3f-124">Po włączeniu integracji następuje utworzenie pakietu i plików eksportu danych oraz ustawienie częstotliwości.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-124">When the integration is turned on, the data export package and files are created, and the frequency is set.</span></span> <span data-ttu-id="ebf3f-125">W razie potrzeby można zmienić tę częstotliwość.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-125">You can change this frequency as you require.</span></span>

<span data-ttu-id="ebf3f-126">Aby uzyskać więcej informacji o kontach magazynu w usłudze Azure i ciągach połączeń z usługą Azure Storage, zobacz następujące tematy poświęcone usłudze Azure:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-126">For more information about Azure storage accounts and Azure Storage connection strings, see the following Azure topics:</span></span>

- [<span data-ttu-id="ebf3f-127">Konta magazynu w usłudze Azure — informacje</span><span class="sxs-lookup"><span data-stu-id="ebf3f-127">About Azure storage accounts</span></span>](https://docs.microsoft.com/azure/storage/common/storage-create-storage-account?toc=%2fazure%2fstorage%2ffiles%2ftoc.json)
- [<span data-ttu-id="ebf3f-128">Konfigurowanie ciągów połączeń z usługą Azure Storage</span><span class="sxs-lookup"><span data-stu-id="ebf3f-128">Configure Azure Storage connection strings</span></span>](https://docs.microsoft.com/azure/storage/common/storage-configure-connection-string)

### <a name="technical-details-when-payroll-integration-is-enabled"></a><span data-ttu-id="ebf3f-129">Dane techniczne, gdy integracja listy płac jest włączona</span><span class="sxs-lookup"><span data-stu-id="ebf3f-129">Technical details when payroll integration is enabled</span></span>

<span data-ttu-id="ebf3f-130">Włączenie integracji listy płac ma dwa główne skutki:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-130">Turning on the payroll integration has two primary effects:</span></span>

- <span data-ttu-id="ebf3f-131">Zostanie utworzony projekt eksportu danych o nazwie „Eksport integracji list płac”.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-131">A data export project named "Payroll integration export" is created.</span></span> <span data-ttu-id="ebf3f-132">Ten projekt zawiera podmioty i pola wymagane do integracji listy płac.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-132">This project contains the entities and fields required for the payroll integration.</span></span> <span data-ttu-id="ebf3f-133">Aby sprawdzić projekt, przejdź do **Administracja systemu**, wybierz kafelek **Zarządzanie danymi**, a następnie otwórz projekt danych z listy projektów.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-133">To examine the project, go to **System administration**, select the **Data management** tile, and then open the data project from the list of projects.</span></span>
- <span data-ttu-id="ebf3f-134">To zadanie wsadowe wykonuje projekt eksportu danych, szyfruje otrzymany pakiet danych i przesyła plik pakietu danych do punktu końcowego SFTP skonfigurowanego na ekranie **Integracja konfiguracji**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-134">This batch job executes the data export project, encrypts the resulting data package, and transfers the data package file to the SFTP endpoint configured on the **Integration configuration** screen.</span></span>

> [!NOTE]
> <span data-ttu-id="ebf3f-135">Pakiet danych przesłany do punktu końcowego SFTP jest szyfrowany przy użyciu klucza unikalnego dla pakietu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-135">The data package transferred to the SFTP endpoint is encrypted using a key that is unique to the package.</span></span> <span data-ttu-id="ebf3f-136">Klucz to Azure Key Vault dostępny jedynie przez Ceridian.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-136">The key is in an Azure Key Vault that is accessible only by Ceridian.</span></span> <span data-ttu-id="ebf3f-137">Nie jest możliwe odszyfrowanie i sprawdzenie zawartości pakietu danych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-137">It is not possible to decrypt and examine the data package contents.</span></span> <span data-ttu-id="ebf3f-138">Jeśli chcesz sprawdzić zawartość pakietu danych, musisz ręcznie wyeksportować projekt danych „Eksportu integracji płac”, pobrać go, a następnie otworzyć.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-138">If you need to examine the contents of the data package, you need to export the "Payroll integration export" data project manually, download it, and then open it.</span></span> <span data-ttu-id="ebf3f-139">Ręczny eksport nie zastosuje szyfrowania ani nie dokona transferu pakietu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-139">Manual export will not apply encryption or transfer the package.</span></span>

## <a name="configure-your-data"></a><span data-ttu-id="ebf3f-140">Konfigurowanie danych</span><span class="sxs-lookup"><span data-stu-id="ebf3f-140">Configure your data</span></span> 

<span data-ttu-id="ebf3f-141">Aby przetwarzać listę płac, należy skonfigurować dane kadrowe w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-141">To process payroll, you must configure human resource data in Talent.</span></span> <span data-ttu-id="ebf3f-142">Należy skonfigurować dane organizacyjne, takie jak funkcje i stanowiska, oraz informacje o wynagrodzeniach i świadczeniach.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-142">You must set up organizational data, such as jobs and positions, together with benefits and compensation information.</span></span> <span data-ttu-id="ebf3f-143">Informacje te stanowią zasób danych o zatrudnieniu, wynagrodzeniach i potrąceniach, które są wymagane do wygenerowania płacy pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-143">This information provides the employment, pay, and deduction information that is required in order to generate employee pay.</span></span>

### <a name="human-resource-data"></a><span data-ttu-id="ebf3f-144">Dane kadrowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-144">Human resource data</span></span>

#### <a name="benefits"></a><span data-ttu-id="ebf3f-145">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-145">Benefits</span></span> 

<span data-ttu-id="ebf3f-146">Moduł Zasoby ludzkie oferuje narzędzia do konfigurowania i obsługi świadczeń, potrąceń i planów wynagrodzeń pracowników, które organizacja oferuje swoim pracownikom lub przetwarza w ich imieniu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-146">Human resources provides tools for the setup and maintenance of the benefits, deductions, and worker compensation plans that an organization offers or processes for its workers.</span></span>

<span data-ttu-id="ebf3f-147">Podczas tworzenia świadczeń należy wziąć pod uwagę następujące dane i konfiguracje używane w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-147">When you create benefits, keep in mind the following data and configurations that are used in Dayforce.</span></span>

##### <a name="benefit-plans"></a><span data-ttu-id="ebf3f-148">Plany świadczeń</span><span class="sxs-lookup"><span data-stu-id="ebf3f-148">Benefit plans</span></span>

- <span data-ttu-id="ebf3f-149">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-149">Plan (required)</span></span>
- <span data-ttu-id="ebf3f-150">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-150">Type (required)</span></span>
- <span data-ttu-id="ebf3f-151">Wpływ na listę płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-151">Payroll impact (required)</span></span>
- <span data-ttu-id="ebf3f-152">Odzyskaj zaległości</span><span class="sxs-lookup"><span data-stu-id="ebf3f-152">Recover arrears</span></span>
- <span data-ttu-id="ebf3f-153">Metoda potrącenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-153">Deduction method</span></span>
- <span data-ttu-id="ebf3f-154">Priorytet potrącenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-154">Deduction priority</span></span>
- <span data-ttu-id="ebf3f-155">Okres limitu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-155">Limit period</span></span>
- <span data-ttu-id="ebf3f-156">Kwota limitu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-156">Limit amount</span></span>

##### <a name="benefits"></a><span data-ttu-id="ebf3f-157">Świadczenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-157">Benefits</span></span>

- <span data-ttu-id="ebf3f-158">Plan (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-158">Plan (required)</span></span>
- <span data-ttu-id="ebf3f-159">Typ (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-159">Type (required)</span></span>
- <span data-ttu-id="ebf3f-160">Opcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-160">Option (required)</span></span>
- <span data-ttu-id="ebf3f-161">Identyfikator świadczenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-161">Benefit ID (required)</span></span>
- <span data-ttu-id="ebf3f-162">Częstotliwość</span><span class="sxs-lookup"><span data-stu-id="ebf3f-162">Frequency</span></span>
- <span data-ttu-id="ebf3f-163">Podstawa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-163">Basis</span></span>
- <span data-ttu-id="ebf3f-164">Kwota lub stawka</span><span class="sxs-lookup"><span data-stu-id="ebf3f-164">Amount or rate</span></span>
- <span data-ttu-id="ebf3f-165">Kod zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-165">Earning code</span></span>

##### <a name="supported-frequencies"></a><span data-ttu-id="ebf3f-166">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="ebf3f-166">Supported frequencies</span></span> 

- <span data-ttu-id="ebf3f-167">Tygodniowa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-167">Weekly</span></span>
- <span data-ttu-id="ebf3f-168">Co dwa tygodnie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-168">Bi-weekly</span></span>
- <span data-ttu-id="ebf3f-169">Co pół miesiąca</span><span class="sxs-lookup"><span data-stu-id="ebf3f-169">Semi-monthly</span></span>
- <span data-ttu-id="ebf3f-170">Miesięczne</span><span class="sxs-lookup"><span data-stu-id="ebf3f-170">Monthly</span></span>

##### <a name="supported-bases"></a><span data-ttu-id="ebf3f-171">Obsługiwane podstawy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-171">Supported bases</span></span> 

- <span data-ttu-id="ebf3f-172">Stała kwota</span><span class="sxs-lookup"><span data-stu-id="ebf3f-172">Fixed amount</span></span>
- <span data-ttu-id="ebf3f-173">Procent zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-173">Percent of earnings</span></span>
- <span data-ttu-id="ebf3f-174">Godziny płatne</span><span class="sxs-lookup"><span data-stu-id="ebf3f-174">Productive hours</span></span>

<span data-ttu-id="ebf3f-175">System Dayforce tworzy następujące potrącenia w oparciu o wpływ na listę płac zdefiniowany w planie świadczeń.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-175">Dayforce creates the following deductions, based on the payroll impact that is defined on the benefit plan.</span></span>

| <span data-ttu-id="ebf3f-176">Wybór w aplikacji Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-176">Selection in Talent</span></span>        | <span data-ttu-id="ebf3f-177">Wynik w systemie Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-177">Result in Dayforce</span></span>                            |
|----------------------------|-----------------------------------------------|
| <span data-ttu-id="ebf3f-178">None</span><span class="sxs-lookup"><span data-stu-id="ebf3f-178">None</span></span>                       | <span data-ttu-id="ebf3f-179">Nie jest tworzone żadne potrącenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-179">No deduction is created.</span></span>                      |
| <span data-ttu-id="ebf3f-180">Tylko potrącenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-180">Deduction only</span></span>             | <span data-ttu-id="ebf3f-181">Jest tworzone potrącenie od pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-181">An employee deduction is created.</span></span>             |
| <span data-ttu-id="ebf3f-182">Tylko udział</span><span class="sxs-lookup"><span data-stu-id="ebf3f-182">Contribution only</span></span>          | <span data-ttu-id="ebf3f-183">Jest tworzone potrącenie od pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-183">An employer deduction is created.</span></span>             |
| <span data-ttu-id="ebf3f-184">Potrącenie i udział</span><span class="sxs-lookup"><span data-stu-id="ebf3f-184">Deduction and contribution</span></span> | <span data-ttu-id="ebf3f-185">Są tworzone potrącenia od pracownika i pracodawcy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-185">Employee and employer deductions are created.</span></span> |

<span data-ttu-id="ebf3f-186">Aby uzyskać więcej informacji o sposobie definiowania programu świadczeń i zarządzania nim, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-186">For more information about how to define and manage a benefits program, see the following topics:</span></span>

- [<span data-ttu-id="ebf3f-187">Dostarczanie programu świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="ebf3f-187">Deliver an employee benefits program</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/deliver-employee-benefits-program)
- [<span data-ttu-id="ebf3f-188">Tworzenie nowego świadczenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-188">Create a new benefit</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/create-new-benefit)
- [<span data-ttu-id="ebf3f-189">Definiowanie zasad i reguł uprawnień do świadczenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-189">Define benefit eligibility rules and policies</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-benefit-eligibility-rules-policies)
- [<span data-ttu-id="ebf3f-190">Rejestrowanie i usuwanie świadczeń dla pracowników</span><span class="sxs-lookup"><span data-stu-id="ebf3f-190">Enroll and remove benefits from workers</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-remove-benefits-workers)

#### <a name="compensation"></a><span data-ttu-id="ebf3f-191">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-191">Compensation</span></span> 

<span data-ttu-id="ebf3f-192">Zarządzanie wynagrodzeniami służy do kontrolowania wypłat podstawowego wynagrodzenia i nagród.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-192">Compensation management is used to control the delivery of base pay and awards.</span></span> <span data-ttu-id="ebf3f-193">Stałe podstawowe wynagrodzenie pracownika i podwyżki podstawowego wynagrodzenia są kontrolowane przez plany stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-193">An employee's fixed base pay and merit increases are controlled through fixed compensation plans.</span></span> <span data-ttu-id="ebf3f-194">Płatności motywacyjne, takie jak premie motywacyjne, wypłaty premii, nagrody za wyniki pracy, prawa do nabycia akcji po ustalonej cenie, cesje i nagrody jednorazowe lub okazjonalne są kontrolowane za pomocą systemów wynagrodzeń o zmiennej wysokości.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-194">The payment of incentive pay, such as bonus payments, performance awards, stock options, and grants, and also one-time awards, are controlled through variable compensation plans.</span></span>

<span data-ttu-id="ebf3f-195">Program Dayforce wykorzystuje informacje o wynagrodzeniach do obliczania godzinowej lub rocznej stawki pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-195">Dayforce uses compensation information to calculate an employee's hourly or annual rate.</span></span> <span data-ttu-id="ebf3f-196">Określenie systemów stałych wynagrodzeń i konwersji stawek płac jest wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-196">Fixed compensation plans and pay rate conversions are required.</span></span> <span data-ttu-id="ebf3f-197">Pracownicy muszą być skojarzeni z systemem stałych wynagrodzeń.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-197">Employees must be associated with a fixed compensation plan.</span></span>

<span data-ttu-id="ebf3f-198">Aby uzyskać więcej informacji o planach wynagrodzeń, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-198">For more information about compensation plans, see the following topics:</span></span>

- [<span data-ttu-id="ebf3f-199">Tworzenie planów stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="ebf3f-199">Create fixed compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-fixed-compensation-plans)
- [<span data-ttu-id="ebf3f-200">Tworzenie planów wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="ebf3f-200">Create variable compensation plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-variable-compensation-plans)
- [<span data-ttu-id="ebf3f-201">Opracowywanie struktury i planu pensji/wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="ebf3f-201">Develop salary/compensation structure and plans</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/develop-salary-compensation-structure-plan)
- [<span data-ttu-id="ebf3f-202">Przetwarzanie wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-202">Process compensation</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/process-compensation)
- [<span data-ttu-id="ebf3f-203">Definiowanie procesu związanego z wynagrodzeniem i obliczanie wyników</span><span class="sxs-lookup"><span data-stu-id="ebf3f-203">Define compensation process and calculate results</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-compensation-process-calculate-results)
- [<span data-ttu-id="ebf3f-204">Zarejestrowanie pracownika w systemie stałych wynagrodzeń</span><span class="sxs-lookup"><span data-stu-id="ebf3f-204">Enroll an employee in a fixed compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-fixed-compensation-plan)
- [<span data-ttu-id="ebf3f-205">Zarejestrowanie pracownika w systemie wynagrodzeń o zmiennej wysokości</span><span class="sxs-lookup"><span data-stu-id="ebf3f-205">Enroll an employee in a variable compensation plan</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/enroll-employee-variable-compensation-plan)

#### <a name="jobs"></a><span data-ttu-id="ebf3f-206">Funkcje</span><span class="sxs-lookup"><span data-stu-id="ebf3f-206">Jobs</span></span> 

<span data-ttu-id="ebf3f-207">Funkcja to zbiór zadań i obowiązków, które są wymagane od osoby wykonującej funkcję.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-207">A job is a collection of the tasks and responsibilities that are required of a person who performs a job.</span></span> <span data-ttu-id="ebf3f-208">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-208">For more information, see the following topics:</span></span>

- [<span data-ttu-id="ebf3f-209">Konfigurowanie składników funkcji</span><span class="sxs-lookup"><span data-stu-id="ebf3f-209">Setting up the components of a job</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-job)
- [<span data-ttu-id="ebf3f-210">Definiowanie nowych zadań</span><span class="sxs-lookup"><span data-stu-id="ebf3f-210">Define new jobs</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-jobs)

##### <a name="positions"></a><span data-ttu-id="ebf3f-211">Pozycje</span><span class="sxs-lookup"><span data-stu-id="ebf3f-211">Positions</span></span>

<span data-ttu-id="ebf3f-212">Pozycja jest pojedynczym wystąpieniem zadania.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-212">A position is an individual instance of a job.</span></span> <span data-ttu-id="ebf3f-213">Na przykład stanowisko „Menedżer ds. sprzedaży (Wschód)” jest jednym ze stanowisk skojarzonych z funkcją „Menedżer ds. sprzedaży”.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-213">For example, the "Sales manager (East)" position is one of the positions that are associated with the "Sales manager" job.</span></span> <span data-ttu-id="ebf3f-214">Stanowisko istnieje w dziale.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-214">A position exists in a department.</span></span> <span data-ttu-id="ebf3f-215">Z każdym stanowiskiem może być skojarzony tylko jeden pracownik.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-215">Only one worker can be associated with each position.</span></span>

<span data-ttu-id="ebf3f-216">Podczas konfigurowania stanowisk pamiętaj o następujących danych i konfiguracjach:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-216">Keep the following data and configuration in mind when you set up positions:</span></span>

- <span data-ttu-id="ebf3f-217">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-217">Position (required)</span></span>
- <span data-ttu-id="ebf3f-218">Opis (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-218">Description (required)</span></span>
- <span data-ttu-id="ebf3f-219">Funkcja (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-219">Job (required)</span></span>
- <span data-ttu-id="ebf3f-220">Dział (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-220">Department (required)</span></span>
- <span data-ttu-id="ebf3f-221">Typ stanowiska (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-221">Position type (required)</span></span>
- <span data-ttu-id="ebf3f-222">W przeliczeniu na pełne etaty</span><span class="sxs-lookup"><span data-stu-id="ebf3f-222">Full-time equivalent</span></span>
- <span data-ttu-id="ebf3f-223">Zwykłe godziny (rocznie) (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-223">Annual regular hours (required)</span></span>
- <span data-ttu-id="ebf3f-224">Zapłacone przez firmę (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-224">Paid by legal entity (required)</span></span>
- <span data-ttu-id="ebf3f-225">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-225">Pay cycle (required)</span></span>
- <span data-ttu-id="ebf3f-226">Domyślny wymiar finansowy — Centrum kosztu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-226">Default financial dimension – Cost center (required)</span></span>
- <span data-ttu-id="ebf3f-227">Przypisanie pracownika — Pracownik, rozpoczęcie przypisania, zakończenia przypisania, kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-227">Worker assignment – Worker, assignment start, assignment end, reason code</span></span>

<span data-ttu-id="ebf3f-228">Jeśli z tą samą funkcją jest skojarzonych wiele stanowisk w tym samym dziale, są one konsolidowane w jedno stanowisko w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-228">If multiple positions in the same department are associated with the same job, they are consolidated into a single position in Dayforce.</span></span>

<span data-ttu-id="ebf3f-229">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-229">For more information, see the following topics:</span></span>

- [<span data-ttu-id="ebf3f-230">Organizowanie pracowników za pomocą działów, funkcji i stanowisk</span><span class="sxs-lookup"><span data-stu-id="ebf3f-230">Organize your workforce using departments, jobs, and positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/departments-jobs-positions#positions)
- [<span data-ttu-id="ebf3f-231">Konfigurowanie stanowisk</span><span class="sxs-lookup"><span data-stu-id="ebf3f-231">Set up positions</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/set-up-positions)

#### <a name="departments"></a><span data-ttu-id="ebf3f-232">Działy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-232">Departments</span></span>

<span data-ttu-id="ebf3f-233">Dział to jednostka operacyjna należąca do kategorii lub obszaru funkcjonalnego organizacji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-233">A department is an operating unit that represents a category or functional area of an organization.</span></span> <span data-ttu-id="ebf3f-234">Dział jest odpowiedzialny za określony obszar organizacji, np. sprzedaż, księgowość lub zasoby ludzkie.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-234">A department is responsible for a specific area of the organization, such as sales, accounting, or human resources.</span></span> <span data-ttu-id="ebf3f-235">Działy pozwalają tworzyć raporty dotyczące obszarów funkcyjnych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-235">You can use departments to report on functional areas.</span></span> <span data-ttu-id="ebf3f-236">Działy mogą mieć odpowiedzialność zysków i strat.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-236">Departments might have profit and loss responsibility.</span></span>

<span data-ttu-id="ebf3f-237">Aby uzyskać więcej informacji, zobacz następujące tematy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-237">For more information, see the following topics:</span></span>

- [<span data-ttu-id="ebf3f-238">Tworzenie działu i kojarzenie go z hierarchią działów</span><span class="sxs-lookup"><span data-stu-id="ebf3f-238">Create a department and associate it with the department hierarchy</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/talent/create-department-add-department-hierarchy)
- [<span data-ttu-id="ebf3f-239">Definiowanie nowych działów</span><span class="sxs-lookup"><span data-stu-id="ebf3f-239">Define new departments</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/fin-and-ops/hr/tasks/define-new-departments)

#### <a name="pay-cycles-and-pay-periods"></a><span data-ttu-id="ebf3f-240">Cykle płac i okresy płac</span><span class="sxs-lookup"><span data-stu-id="ebf3f-240">Pay cycles and pay periods</span></span>

<span data-ttu-id="ebf3f-241">Cykl kalkulacji płac decyduje o częstotliwości wykonywania sesji obliczania listy płac oraz o konkretnych dniach, kiedy pracownicy otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-241">A pay cycle determines how often payroll is run and the specific days when workers are paid.</span></span> <span data-ttu-id="ebf3f-242">Na przykład cykl kalkulacji płac może być miesięczny, a pracownicy mogą otrzymywać wypłatę w ostatnim dniu miesiąca.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-242">For example, a pay cycle might be monthly, and employees might be paid on the last day of the month.</span></span> <span data-ttu-id="ebf3f-243">Alternatywnie cykl kalkulacji płac może być tygodniowy, a pracownicy dostają wypłatę w każdy wtorek po zakończeniu okresu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-243">Alternatively, a pay cycle might be weekly, and employees might be paid on the Tuesday after the end of the pay period.</span></span> <span data-ttu-id="ebf3f-244">Cykle kalkulacji płac są przypisywane do stanowisk w celu kontrolowania, kiedy pracownicy na tych stanowiskach otrzymują zapłatę.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-244">Pay cycles are assigned to positions to control when workers in those positions are paid.</span></span>

<span data-ttu-id="ebf3f-245">Po utworzeniu cykli kalkulacji płac można wygenerować okresy kalkulacji płac dla każdego cyklu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-245">After you create pay cycles, you can generate pay periods for each cycle.</span></span> <span data-ttu-id="ebf3f-246">Każdy okres kalkulacji płac zawiera domyślną datę płatności, która bazuje na podanych przez Ciebie informacjach.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-246">Each pay period includes a default payment date that is based on information that you provide.</span></span> <span data-ttu-id="ebf3f-247">Można jednak zmodyfikować domyślną datę płatności w okresie kalkulacji płac, co pozwala stosować wyjątki, np. gdy data płatności przypada na dzień wolny od pracy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-247">However, you can modify the default payment date in a pay period to allow for exceptions, such as when the payment date falls on a holiday.</span></span>

<span data-ttu-id="ebf3f-248">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-248">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="ebf3f-249">Cykl kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-249">Pay cycle (required)</span></span>
- <span data-ttu-id="ebf3f-250">Częstotliwość cyklu kalkulacji płac (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-250">Pay cycle frequency (required)</span></span>
- <span data-ttu-id="ebf3f-251">Data rozpoczęcia okresu (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-251">Period start date (first pay period required)</span></span>
- <span data-ttu-id="ebf3f-252">Domyślna data płatności (pierwszy okres kalkulacji płac jest wymagany)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-252">Default payment date (first pay period required)</span></span>

<span data-ttu-id="ebf3f-253">Te informacje są integrowane z usługą Dayforce jako grupy płac oraz dzielone na kraje lub regiony dla każdego cyklu kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-253">This information is integrated with Dayforce as pay groups, and is separated by country or region for each pay cycle.</span></span> <span data-ttu-id="ebf3f-254">Przed integracją musi być wygenerowany co najmniej jeden okres kalkulacji płac.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-254">At least one pay period must be generated before integration.</span></span> <span data-ttu-id="ebf3f-255">System Dayforce generuje kalendarze grup płac i daty płatności na podstawie daty rozpoczęcia pierwszego okresu kalkulacji płac i domyślnej daty płatności ustawionej w aplikacji Talent.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-255">Dayforce generates pay group calendars and payment dates, based on the start date of the first pay period and the default payment date that is set up in Talent.</span></span>

#### <a name="earning-codes"></a><span data-ttu-id="ebf3f-256">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-256">Earning codes</span></span>

<span data-ttu-id="ebf3f-257">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-257">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="ebf3f-258">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-258">The codes have various parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span>

<span data-ttu-id="ebf3f-259">Poniższe informacje są używane w programie Dayforce:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-259">The following information is used in Dayforce:</span></span>

- <span data-ttu-id="ebf3f-260">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-260">Earning Code (required)</span></span>
- <span data-ttu-id="ebf3f-261">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-261">Description</span></span>
- <span data-ttu-id="ebf3f-262">Jednostka miary</span><span class="sxs-lookup"><span data-stu-id="ebf3f-262">Unit of measure</span></span>
- <span data-ttu-id="ebf3f-263">Płatne</span><span class="sxs-lookup"><span data-stu-id="ebf3f-263">Productive</span></span>

### <a name="worker-data"></a><span data-ttu-id="ebf3f-264">Dane pracowników</span><span class="sxs-lookup"><span data-stu-id="ebf3f-264">Worker data</span></span>

<span data-ttu-id="ebf3f-265">Dokumenty o różnych typach posiadanych pracowników są ważne dla informatycznych systemów kadrowych i płacowych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-265">Records for the various types of workers that you have are important to your human resources and payroll systems.</span></span> <span data-ttu-id="ebf3f-266">Wprowadzone informacje mogą służyć do monitorowania pracowników i danych osobowych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-266">The information that you enter can be used to track workers and personal information.</span></span>

<span data-ttu-id="ebf3f-267">Można przechowywać następujące informacje o pracownikach:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-267">You can maintain the following information for workers:</span></span>

- <span data-ttu-id="ebf3f-268">**Podstawowe** — Podstawowe informacje o pracowniku, takie jak dane kontaktowe, demograficzne, identyfikacyjne, informacje o rodzinie, stosunek do służby wojskowej, status emigranta oraz dane kontaktowe dla nagłych wypadków.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-268">**Basic** – Maintain basic information about a worker, such as contact information, demographic information, identification information, family information, military service status, expatriate information, and personal and emergency contacts.</span></span>
- <span data-ttu-id="ebf3f-269">**Zatrudnienie** — Informacje o zatrudnieniu pracownika, takie jak przynależność do firmy lub organizacji, przypisanie stanowiska, daty rozpoczęcia i zakończenia, prawo do zatrudnienia, warunki zatrudnienia, emerytura, urlop i informacje o przeniesieniu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-269">**Employment** – Maintain information about a worker's employment, such as company or organization affiliation, position assignment, start and end dates, work eligibility, terms of employment, pension, vacation, and relocation information.</span></span>
- <span data-ttu-id="ebf3f-270">**Urlopy i nieobecności** — Informacje o nieobecności pracownika, takie jak kalendarze pracy, transakcje nieobecności i ustawienia nieobecności.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-270">**Leave and absence** – Maintain information about a worker's absences, such as working calendars, absence transactions, and absence setup.</span></span>
- <span data-ttu-id="ebf3f-271">**Wynagrodzenia i płace** — Informacje o planach wynagrodzeń i płacach pracownika, takie jak rejestracja w planie, nagrody, wydajność, prowizje, informacje podatkowe, odejście na emeryturę i potrącenia z wynagrodzenia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-271">**Compensation and payroll** – Maintain information about a worker's compensation plans and payroll information, such as plan enrollment, awards, performance, commission, tax information, retirement, and salary deductions.</span></span>

<span data-ttu-id="ebf3f-272">Podczas wprowadzania danych pracownika należy wziąć pod uwagę następujące dane i konfiguracje używane w programie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-272">When you enter worker information, keep in mind the following data and configurations that are used in Dayforce.</span></span>

#### <a name="general-information"></a><span data-ttu-id="ebf3f-273">Informacje ogólne</span><span class="sxs-lookup"><span data-stu-id="ebf3f-273">General information</span></span>

- <span data-ttu-id="ebf3f-274">Numer pracownika (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-274">Personnel number (required)</span></span>
- <span data-ttu-id="ebf3f-275">Imię (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-275">First name (required)</span></span>
- <span data-ttu-id="ebf3f-276">Nazwisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-276">Last name (required)</span></span>
- <span data-ttu-id="ebf3f-277">Drugie imię</span><span class="sxs-lookup"><span data-stu-id="ebf3f-277">Middle name</span></span>
- <span data-ttu-id="ebf3f-278">Data stażu pracy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-278">Seniority date</span></span>
- <span data-ttu-id="ebf3f-279">Znane jako</span><span class="sxs-lookup"><span data-stu-id="ebf3f-279">Known as</span></span>

#### <a name="personal-information"></a><span data-ttu-id="ebf3f-280">Informacje osobiste</span><span class="sxs-lookup"><span data-stu-id="ebf3f-280">Personal information</span></span>

- <span data-ttu-id="ebf3f-281">Stan cywilny (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-281">Marital status (required)</span></span>
- <span data-ttu-id="ebf3f-282">Data urodzenia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-282">Birth date (required)</span></span>
- <span data-ttu-id="ebf3f-283">Płeć (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-283">Gender (required)</span></span>
- <span data-ttu-id="ebf3f-284">Osoba niepełnosprawna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-284">Person with disabilities</span></span>
- <span data-ttu-id="ebf3f-285">Obywatelstwo (kraj/region) (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-285">Nationality country region (only for Mexico)</span></span>

#### <a name="address-information"></a><span data-ttu-id="ebf3f-286">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-286">Address information</span></span>

- <span data-ttu-id="ebf3f-287">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-287">Primary (required)</span></span>
- <span data-ttu-id="ebf3f-288">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-288">Country/region (required)</span></span>
- <span data-ttu-id="ebf3f-289">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-289">Postal code (required)</span></span>
- <span data-ttu-id="ebf3f-290">Numer domu (wymagane) (jedynie w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-290">Street Number (required) (Only for Mexico)</span></span>
- <span data-ttu-id="ebf3f-291">Dodatkowe określenie budynku (tylko w przypadku Meksyku)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-291">Building Complement (Only for Mexico)</span></span>
- <span data-ttu-id="ebf3f-292">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-292">City (required)</span></span>
- <span data-ttu-id="ebf3f-293">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-293">State (required)</span></span>
- <span data-ttu-id="ebf3f-294">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-294">County (required)</span></span>

#### <a name="contact-information"></a><span data-ttu-id="ebf3f-295">Informacje o kontakcie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-295">Contact information</span></span> 

- <span data-ttu-id="ebf3f-296">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-296">Primary (required)</span></span>
- <span data-ttu-id="ebf3f-297">Nazwa osoby kontaktowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-297">Contact number (required)</span></span>
- <span data-ttu-id="ebf3f-298">Wewnętrzny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-298">Extension</span></span>

#### <a name="payroll-information-and-earning-codes"></a><span data-ttu-id="ebf3f-299">Informacje płacowe i kody zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-299">Payroll information and earning codes</span></span>

<span data-ttu-id="ebf3f-300">Pracownicy mogą mieć przypisane określone zarobki z określoną częstotliwością wypłat oraz mieć ustawioną preferowaną metodę płatności.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-300">Employees may be assigned specific earnings at a given frequency of payment and have a preferred payment method.</span></span> <span data-ttu-id="ebf3f-301">Następujące pola są używane w usłudze Dayforce w celu zagwarantowania, że te ustawienia i preferencje są wykorzystywane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-301">The following fields are used in Dayforce to help guarantee that those preferences and settings are used.</span></span>

##### <a name="earning-codes"></a><span data-ttu-id="ebf3f-302">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-302">Earning codes</span></span>

- <span data-ttu-id="ebf3f-303">Stanowisko (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-303">Position (required)</span></span>
- <span data-ttu-id="ebf3f-304">Kod zarobków (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-304">Earning Code (required)</span></span>
- <span data-ttu-id="ebf3f-305">Częstotliwość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-305">Frequency (required)</span></span>
- <span data-ttu-id="ebf3f-306">Kwota (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-306">Amount (required)</span></span>

##### <a name="payroll-information"></a><span data-ttu-id="ebf3f-307">Informacje listy płac</span><span class="sxs-lookup"><span data-stu-id="ebf3f-307">Payroll information</span></span>

- <span data-ttu-id="ebf3f-308">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="ebf3f-308">Payment Method</span></span>
- <span data-ttu-id="ebf3f-309">Region gospodarczy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-309">Economic Region (required)</span></span>
- <span data-ttu-id="ebf3f-310">Identyfikator świadczeń pracownika etatowego</span><span class="sxs-lookup"><span data-stu-id="ebf3f-310">Employee Benefits ID</span></span>
- <span data-ttu-id="ebf3f-311">Numer dowodu osobistego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-311">National ID Number (required)</span></span>
- <span data-ttu-id="ebf3f-312">Numer książeczki wojskowej</span><span class="sxs-lookup"><span data-stu-id="ebf3f-312">Military Service Number</span></span>
- <span data-ttu-id="ebf3f-313">Identyfikator zmiany (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-313">Shift ID (required)</span></span>
- <span data-ttu-id="ebf3f-314">Numer identyfikacji podatkowej (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-314">Tax Number (required)</span></span>
- <span data-ttu-id="ebf3f-315">Identyfikator związku (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-315">Union ID (required)</span></span>
- <span data-ttu-id="ebf3f-316">Identyfikator dnia roboczego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-316">Work Day ID (required)</span></span>
- <span data-ttu-id="ebf3f-317">Numer pozwolenia na pracę</span><span class="sxs-lookup"><span data-stu-id="ebf3f-317">Work Permit Number</span></span>

> [!NOTE]
> <span data-ttu-id="ebf3f-318">W Meksyku obsługiwane metody płatności to **Gotówka**, **Czek** (fizyczny czek wystawiany przez firmę) i **Płatność elektroniczna**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-318">For the payment method, Mexico supports **Cash**, **Check** (the company's physical check), and **Electronic Payment**.</span></span> <span data-ttu-id="ebf3f-319">Jeśli metoda płatności nie zostanie określona, domyślnie będzie używana metoda **Czek**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-319">If np payment method is specified, **Check** is used by default.</span></span>

#### <a name="employment-details"></a><span data-ttu-id="ebf3f-320">Szczegóły zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-320">Employment details</span></span>

<span data-ttu-id="ebf3f-321">Historia szczegółów zatrudnienia pełni rolę kluczowych informacji przy ustalaniu statusów zatrudnienia, zwolnienia i ponownego zatrudnienia pracownika etatowego w systemie Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-321">Employment detail history is used as key information to derive an employee's hire, termination, and rehire statuses in Dayforce.</span></span> <span data-ttu-id="ebf3f-322">W rozwiązaniu Dayforce może istnieć tylko jeden aktywny rekord zatrudnienia na raz.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-322">Dayforce supports only one active employment record at a time.</span></span>

- <span data-ttu-id="ebf3f-323">Data rozpoczęcia zatrudnienia (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-323">Employment start date (required)</span></span>
- <span data-ttu-id="ebf3f-324">Data zakończenia zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-324">Employment end date</span></span>
- <span data-ttu-id="ebf3f-325">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-325">Start date</span></span>
- <span data-ttu-id="ebf3f-326">Dopasowana data rozpoczęcia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-326">Adjusted start date</span></span>
- <span data-ttu-id="ebf3f-327">Data zakończenia (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-327">Termination date (required upon termination)</span></span>
- <span data-ttu-id="ebf3f-328">Powód rozwiązania umowy (wymagane po rozwiązaniu stosunku pracy)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-328">Termination reason (required upon termination)</span></span>

<span data-ttu-id="ebf3f-329">Kluczowe daty pracownika są obliczane na podstawie następujących informacji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-329">An employee's key dates are derived by using the following information.</span></span>

| <span data-ttu-id="ebf3f-330">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-330">Talent</span></span>                | <span data-ttu-id="ebf3f-331">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-331">Dayforce</span></span>                                                                                             |
|-----------------------|------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ebf3f-332">Ostatnia data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-332">Most recent hire date</span></span> | <span data-ttu-id="ebf3f-333">Rozpoczęcie pracy w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-333">Employment start of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="ebf3f-334">Data zakończenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-334">Termination date</span></span>      | <span data-ttu-id="ebf3f-335">Data zakończenia zatrudnienia w bieżącym rekordzie historii niezakończonego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-335">Termination date of current non-terminated employment history record</span></span>                                 |
| <span data-ttu-id="ebf3f-336">Rozpoczęcie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-336">Start date</span></span>            | <span data-ttu-id="ebf3f-337">Skorygowana data rozpoczęcia, data rozpoczęcia lub rozpoczęcie zatrudnienia w bieżącym rekordzie historii nieaktywnego zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-337">Adjusted start date, start date, or employment start of current non-active employment history record</span></span> |
| <span data-ttu-id="ebf3f-338">Pierwotna data zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-338">Original hire date</span></span>    | <span data-ttu-id="ebf3f-339">Rozpoczęcie zatrudnienia w najwcześniejszym rekordzie historii zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-339">Employment start of earliest employment history record</span></span>                                               |

#### <a name="compensation"></a><span data-ttu-id="ebf3f-340">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-340">Compensation</span></span>

<span data-ttu-id="ebf3f-341">Plan stałych wynagrodzeń musi być skojarzony z podstawowym stanowiskiem każdego pracownika w okresie zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-341">A fixed compensation plan must be associated with every employee's primary position throughout an employment period.</span></span> <span data-ttu-id="ebf3f-342">Okres ten rozpoczyna się w dniu zatrudnienia pracownika (lub rozpoczęcia zatrudnienia) i trwa do momentu zakończenia zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-342">This period starts on the date that the employee was hired (or the employment start date) and continues until termination.</span></span>

- <span data-ttu-id="ebf3f-343">Data obowiązywania (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-343">Effective Date (required)</span></span>
- <span data-ttu-id="ebf3f-344">Data ważności</span><span class="sxs-lookup"><span data-stu-id="ebf3f-344">Expiration date</span></span>
- <span data-ttu-id="ebf3f-345">Stawka płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-345">Pay Rate (required)</span></span>
- <span data-ttu-id="ebf3f-346">Konwersje stawek płacy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-346">Pay Rate Conversions (required)</span></span>
- <span data-ttu-id="ebf3f-347">Równowartość roczna (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-347">Annual equivalent (required)</span></span>
- <span data-ttu-id="ebf3f-348">Równowartość godzinowa (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-348">Hourly equivalent (required)</span></span>

<span data-ttu-id="ebf3f-349">Jeśli pracownik rozliczany godzinowo zajmuje kilka stanowisk, stałe wynagrodzenie na podstawowym stanowisku jest importowane do systemu Dayforce jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-349">If an hourly employee has multiple positions, the fixed compensation of the primary position is imported into Dayforce as the employee-level base rate/salary.</span></span> <span data-ttu-id="ebf3f-350">Dla stanowisk dodatkowych stawka godzinowa jest zapisywana na odpowiednich stanowiskach w usłudze Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-350">For non-primary positions, the hourly rate is saved to the corresponding position in Dayforce.</span></span>

<span data-ttu-id="ebf3f-351">Jeśli pracownik na stawce stałej zajmuje kilka stanowisk, skumulowana stawka godzinowa i roczne wynagrodzenie ze wszystkich aktywnych stanowisk są używane jako podstawowa stawka/wynagrodzenie na poziomie pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-351">If a salaried employee has multiple positions, the cumulative hour rate and annual salary across all active positions are derived and used as the employee-level base rate/salary.</span></span>

#### <a name="identification-numbers"></a><span data-ttu-id="ebf3f-352">Numery identyfikacyjne</span><span class="sxs-lookup"><span data-stu-id="ebf3f-352">Identification numbers</span></span>

##### <a name="social-security-identifier"></a><span data-ttu-id="ebf3f-353">Numer ubezpieczenia społecznego</span><span class="sxs-lookup"><span data-stu-id="ebf3f-353">Social Security identifier</span></span> 

<span data-ttu-id="ebf3f-354">Każdy pracownik musi mieć jeden identyfikator podstawowy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-354">Every employee must have one primary identifier.</span></span> <span data-ttu-id="ebf3f-355">Identyfikator ten musi być typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-355">This identifier must be of **SSN** identification type.</span></span> <span data-ttu-id="ebf3f-356">W systemie Dayforce jest on automatycznie interpretowany jako numer ubezpieczenia społecznego wymagany w celu zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-356">In Dayforce, it's automatically derived as the employee's Social Security identifier that is required for hire.</span></span>

- <span data-ttu-id="ebf3f-357">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-357">Primary (required)</span></span>
- <span data-ttu-id="ebf3f-358">Typ identyfikacji = „PESEL”</span><span class="sxs-lookup"><span data-stu-id="ebf3f-358">Identification Type = "SSN"</span></span>
- <span data-ttu-id="ebf3f-359">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-359">Issued Date</span></span>
- <span data-ttu-id="ebf3f-360">Data ważności</span><span class="sxs-lookup"><span data-stu-id="ebf3f-360">Expiration Date</span></span>

<span data-ttu-id="ebf3f-361">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **PESEL**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-361">Employees can declare multiple identification numbers of the **SSN** identification type.</span></span> <span data-ttu-id="ebf3f-362">Jednak tylko rekord oznaczony jako **Podstawowy** jest integrowany z rozwiązaniem Dayforce, niezależnie od tego, czy jest on aktywny, czy wygasły.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-362">However, only the record that is marked as **Primary** is integrated into Dayforce, regardless of whether the number is active or expired.</span></span>

#### <a name="bank-accounts-and-disbursements"></a><span data-ttu-id="ebf3f-363">Konta bankowe i wypłaty</span><span class="sxs-lookup"><span data-stu-id="ebf3f-363">Bank accounts and disbursements</span></span>

<span data-ttu-id="ebf3f-364">Dla każdego pracownika, który wybrał opcję otrzymywania wynagrodzenia przelewami na rachunek bankowy, należy wprowadzić prawidłowe dane konta bankowego.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-364">Valid bank account information must be entered for any employee who chooses to be paid via bank account transfers.</span></span>

| <span data-ttu-id="ebf3f-365">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-365">Talent</span></span>                         | <span data-ttu-id="ebf3f-366">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-366">Dayforce</span></span>                                                                                                    |
|--------------------------------|-------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="ebf3f-367">Numer konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-367">Bank account number (required)</span></span> |                                                                                                             |
| <span data-ttu-id="ebf3f-368">Kod SWIFT (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-368">SWIFT code (required)</span></span>          | <span data-ttu-id="ebf3f-369">Pole **Identyfikator banku** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-369">**Bank ID** field used when processing payroll in Mexico.</span></span>                                                             |
| <span data-ttu-id="ebf3f-370">Numer oddziału (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-370">Branch number (required)</span></span>       |                                                                                                             |
| <span data-ttu-id="ebf3f-371">Typ konta bankowego (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-371">Bank account type (required)</span></span>   | <span data-ttu-id="ebf3f-372">Pole **Typ konta** używane w trakcie przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-372">**Account type** field used when processing payroll in Mexico.</span></span> <span data-ttu-id="ebf3f-373">Obsługiwane wartości **Czekowe** i **Lista płac**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-373">Supported values include **Checking** and **Payroll**.</span></span> |

> [!NOTE]
> <span data-ttu-id="ebf3f-374">Pracownicy, którzy wybiorą otrzymywanie wynagrodzeń przelewami na rachunki bankowe, muszą podać łącze do konta pozostałości, które należy do firmy mającej podstawowy adres w Meksyku i jest skojarzone z prawidłowym kontem bankowym w meksykańskim banku.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-374">Employees who choose to be paid via bank account transfers must provide a link to a remainder account that is under a legal entity that has its primary address in Mexico and associated with a valid bank account from a Mexican bank.</span></span> <span data-ttu-id="ebf3f-375">Wszystkie inne konta pozostałości są ignorowane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-375">All other non-remainder accounts are ignored.</span></span>

#### <a name="address-information"></a><span data-ttu-id="ebf3f-376">Informacje adresowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-376">Address information</span></span>

<span data-ttu-id="ebf3f-377">Każdy pracownik musi mieć jedną lokalizację podstawową.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-377">Every employee must have one primary location.</span></span> <span data-ttu-id="ebf3f-378">W systemie Dayforce ta lokalizacja jest używana do określenia głównego miejsca zamieszkania pracownika w celach podatkowych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-378">In Dayforce, this location is used to determine the employee's primary residence for tax purposes.</span></span>

- <span data-ttu-id="ebf3f-379">Podstawowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-379">Primary (required)</span></span>
- <span data-ttu-id="ebf3f-380">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-380">Country/region (required)</span></span>
- <span data-ttu-id="ebf3f-381">Kod pocztowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-381">Zip/postal code (required)</span></span>
- <span data-ttu-id="ebf3f-382">Ulica (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-382">Street (required)</span></span>
- <span data-ttu-id="ebf3f-383">Numer domu (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-383">Street Number (required)</span></span>
- <span data-ttu-id="ebf3f-384">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="ebf3f-384">Building Complement</span></span>
- <span data-ttu-id="ebf3f-385">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-385">City (required)</span></span>
- <span data-ttu-id="ebf3f-386">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-386">State (required)</span></span>
- <span data-ttu-id="ebf3f-387">Powiat (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-387">County (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-united-states-and-canada"></a><span data-ttu-id="ebf3f-388">Konfigurowanie danych w celu generowania listy płac w Stanach Zjednoczonych i Kanadzie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-388">Configure your data to generate payroll in United States and Canada</span></span>

<span data-ttu-id="ebf3f-389">Jeśli generujesz płace dla pracowników na terenie Stanów Zjednoczonych i Kanady, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-389">If you're generating pay for employees in the United States and Canada, the following elements must be configured:</span></span>

- <span data-ttu-id="ebf3f-390">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-390">Departments are required on positions.</span></span>
- <span data-ttu-id="ebf3f-391">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-391">Cost centers must be set as financial dimensions and must be the first element in the default financial dimension string.</span></span>

> [!NOTE] 
> <span data-ttu-id="ebf3f-392">Można skonfigurować Talent tak, aby Stanowiska umożliwiały określenie działu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-392">You can configure Talent to require that Positions specify a Department.</span></span> <span data-ttu-id="ebf3f-393">Aby to zrobić, przejdź do **stanowisk udostępnionych zasobów ludzkich > Stanowisk > wymagają działów stanowisk**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-393">To do this, go to **Human Resources Shared Positions > Positions > Require departments on positions**.</span></span> <span data-ttu-id="ebf3f-394">Zaleca się, aby to ustawienie zostało wymuszone dla integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-394">We recommend that this setting be enforced for the integration.</span></span>

### <a name="job-types"></a><span data-ttu-id="ebf3f-395">Typy funkcji</span><span class="sxs-lookup"><span data-stu-id="ebf3f-395">Job types</span></span>

<span data-ttu-id="ebf3f-396">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-396">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="ebf3f-397">Typy funkcji są wymagane w celu przetwarzania listy płac w Stanach Zjednoczonych i Kanadzie.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-397">Job types are required in order to process payroll in the United States and Canada.</span></span> <span data-ttu-id="ebf3f-398">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-398">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="ebf3f-399">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-399">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="ebf3f-400">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-400">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-401">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="ebf3f-401">Job type</span></span>   | <span data-ttu-id="ebf3f-402">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-402">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="ebf3f-403">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="ebf3f-403">Hourly</span></span>     | <span data-ttu-id="ebf3f-404">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="ebf3f-404">Hourly</span></span>      |
| <span data-ttu-id="ebf3f-405">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-405">Salaried</span></span>   | <span data-ttu-id="ebf3f-406">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-406">Salaried</span></span>    |

### <a name="position-types"></a><span data-ttu-id="ebf3f-407">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="ebf3f-407">Position types</span></span> 

<span data-ttu-id="ebf3f-408">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-408">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="ebf3f-409">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-409">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="ebf3f-410">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-410">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-411">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="ebf3f-411">Position type</span></span>   | <span data-ttu-id="ebf3f-412">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-412">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="ebf3f-413">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-413">Full-time</span></span>       | <span data-ttu-id="ebf3f-414">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-414">Full time employee</span></span> |
| <span data-ttu-id="ebf3f-415">Część etatu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-415">Part-time</span></span>       | <span data-ttu-id="ebf3f-416">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-416">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="ebf3f-417">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="ebf3f-417">Reason codes</span></span>

<span data-ttu-id="ebf3f-418">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-418">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="ebf3f-419">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-419">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="ebf3f-420">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-420">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-421">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-421">Reason code</span></span>    | <span data-ttu-id="ebf3f-422">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-422">Description</span></span>      | <span data-ttu-id="ebf3f-423">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="ebf3f-423">Applicable scenarios</span></span> |
|----------------|------------------|----------------------|
| <span data-ttu-id="ebf3f-424">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="ebf3f-424">RESIGNATION</span></span>    | <span data-ttu-id="ebf3f-425">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-425">Resignation</span></span>      | <span data-ttu-id="ebf3f-426">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-426">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-427">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="ebf3f-427">TERMINATION</span></span>    | <span data-ttu-id="ebf3f-428">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-428">Termination</span></span>      | <span data-ttu-id="ebf3f-429">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-429">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-430">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="ebf3f-430">RETIREMENT</span></span>     | <span data-ttu-id="ebf3f-431">Emerytura</span><span class="sxs-lookup"><span data-stu-id="ebf3f-431">Retirement</span></span>       | <span data-ttu-id="ebf3f-432">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-432">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-433">INNY</span><span class="sxs-lookup"><span data-stu-id="ebf3f-433">OTHER</span></span>          | <span data-ttu-id="ebf3f-434">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-434">Other Reasons</span></span>    | <span data-ttu-id="ebf3f-435">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-435">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-436">DEATH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-436">DEATH</span></span>          | <span data-ttu-id="ebf3f-437">Śmierć</span><span class="sxs-lookup"><span data-stu-id="ebf3f-437">Death</span></span>            | <span data-ttu-id="ebf3f-438">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-438">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-439">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="ebf3f-439">LEAVEOFABSENCE</span></span> | <span data-ttu-id="ebf3f-440">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="ebf3f-440">Leave of Absence</span></span> | <span data-ttu-id="ebf3f-441">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-441">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-442">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="ebf3f-442">CONTRACTEND</span></span>    | <span data-ttu-id="ebf3f-443">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-443">End of Contract</span></span>  | <span data-ttu-id="ebf3f-444">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-444">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-445">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="ebf3f-445">SALARYCHANGE</span></span>   | <span data-ttu-id="ebf3f-446">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-446">Change of Salary</span></span> | <span data-ttu-id="ebf3f-447">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-447">Compensation</span></span>         |

### <a name="marital-status"></a><span data-ttu-id="ebf3f-448">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-448">Marital status</span></span>

<span data-ttu-id="ebf3f-449">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-449">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ebf3f-450">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-450">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="ebf3f-451">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-451">Talent</span></span>                 | <span data-ttu-id="ebf3f-452">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-452">Dayforce</span></span>             |
|------------------------|----------------------|
| <span data-ttu-id="ebf3f-453">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="ebf3f-453">Married</span></span>                | <span data-ttu-id="ebf3f-454">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="ebf3f-454">Married</span></span>              |
| <span data-ttu-id="ebf3f-455">Jedno</span><span class="sxs-lookup"><span data-stu-id="ebf3f-455">Single</span></span>                 | <span data-ttu-id="ebf3f-456">Jedno</span><span class="sxs-lookup"><span data-stu-id="ebf3f-456">Single</span></span>               |
| <span data-ttu-id="ebf3f-457">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-457">Widowed</span></span>                | <span data-ttu-id="ebf3f-458">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-458">Widowed</span></span>              |
| <span data-ttu-id="ebf3f-459">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="ebf3f-459">Divorced</span></span>               | <span data-ttu-id="ebf3f-460">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="ebf3f-460">Divorced</span></span>             |
| <span data-ttu-id="ebf3f-461">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="ebf3f-461">Registered Partnership</span></span> | <span data-ttu-id="ebf3f-462">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-462">Domestic Partnership</span></span> |
| <span data-ttu-id="ebf3f-463">None</span><span class="sxs-lookup"><span data-stu-id="ebf3f-463">None</span></span>                   | <span data-ttu-id="ebf3f-464">None</span><span class="sxs-lookup"><span data-stu-id="ebf3f-464">None</span></span>                 |
| <span data-ttu-id="ebf3f-465">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-465">Cohabiting</span></span>             | <span data-ttu-id="ebf3f-466">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-466">Cohabiting</span></span>           |

### <a name="gender"></a><span data-ttu-id="ebf3f-467">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="ebf3f-467">Gender</span></span>

<span data-ttu-id="ebf3f-468">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-468">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ebf3f-469">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-469">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="ebf3f-470">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-470">Talent</span></span>       | <span data-ttu-id="ebf3f-471">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-471">Dayforce</span></span>        |
|--------------|-----------------|
| <span data-ttu-id="ebf3f-472">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-472">Male</span></span>         | <span data-ttu-id="ebf3f-473">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-473">Male</span></span>            |
| <span data-ttu-id="ebf3f-474">Kobieta</span><span class="sxs-lookup"><span data-stu-id="ebf3f-474">Female</span></span>       | <span data-ttu-id="ebf3f-475">Kobieta</span><span class="sxs-lookup"><span data-stu-id="ebf3f-475">Female</span></span>          |
| <span data-ttu-id="ebf3f-476">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="ebf3f-476">Non-specific</span></span> | <span data-ttu-id="ebf3f-477">*Nieobsługiwane*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-477">*Not supported*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="ebf3f-478">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-478">Earning codes</span></span>

<span data-ttu-id="ebf3f-479">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-479">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="ebf3f-480">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-480">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="ebf3f-481">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-481">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="ebf3f-482">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="ebf3f-482">Supported frequencies</span></span>

- <span data-ttu-id="ebf3f-483">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-483">All</span></span>
- <span data-ttu-id="ebf3f-484">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="ebf3f-484">EVERYPAY</span></span>
- <span data-ttu-id="ebf3f-485">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="ebf3f-485">EACHPAYPERIOD</span></span>
- <span data-ttu-id="ebf3f-486">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="ebf3f-486">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="ebf3f-487">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="ebf3f-487">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="ebf3f-488">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-488">1OFMTH</span></span>
- <span data-ttu-id="ebf3f-489">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-489">LASTOFMTH</span></span>
- <span data-ttu-id="ebf3f-490">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-490">2OFMTH</span></span>
- <span data-ttu-id="ebf3f-491">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-491">3OFMTH</span></span>
- <span data-ttu-id="ebf3f-492">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-492">4OFMTH</span></span>
- <span data-ttu-id="ebf3f-493">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-493">5OFMTH</span></span>
- <span data-ttu-id="ebf3f-494">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-494">1N2OFMTH</span></span>
- <span data-ttu-id="ebf3f-495">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-495">3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-496">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-496">1N3OFMTH</span></span>
- <span data-ttu-id="ebf3f-497">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-497">1N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-498">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-498">2N3OFMTH</span></span>
- <span data-ttu-id="ebf3f-499">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-499">2N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-500">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-500">1N2N3OFMTH</span></span>
- <span data-ttu-id="ebf3f-501">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-501">1N2N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-502">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-502">1N3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-503">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-503">2N3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-504">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-504">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-505">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="ebf3f-505">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="ebf3f-506">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-506">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="ebf3f-507">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-507">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="ebf3f-508">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-508">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="ebf3f-509">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-509">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="ebf3f-510">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-510">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="ebf3f-511">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-511">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="ebf3f-512">Adresy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-512">Addresses</span></span>

<span data-ttu-id="ebf3f-513">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-513">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="ebf3f-514">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-514">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="ebf3f-515">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-515">Talent</span></span>          | <span data-ttu-id="ebf3f-516">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-516">Dayforce</span></span>              |
|-----------------|-----------------------|
| <span data-ttu-id="ebf3f-517">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="ebf3f-517">Country/Region</span></span>  | <span data-ttu-id="ebf3f-518">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="ebf3f-518">Country Code</span></span>          |
| <span data-ttu-id="ebf3f-519">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-519">Zip/Postal Code</span></span> | <span data-ttu-id="ebf3f-520">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-520">Postal Code</span></span>           |
| <span data-ttu-id="ebf3f-521">Stanowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-521">State</span></span>           | <span data-ttu-id="ebf3f-522">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-522">State Code</span></span>            |
| <span data-ttu-id="ebf3f-523">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="ebf3f-523">City</span></span>            | <span data-ttu-id="ebf3f-524">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="ebf3f-524">City</span></span>                  |
| <span data-ttu-id="ebf3f-525">Powiat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-525">County</span></span>          | <span data-ttu-id="ebf3f-526">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-526">County (Municipality)</span></span> |
| <span data-ttu-id="ebf3f-527">Ulica</span><span class="sxs-lookup"><span data-stu-id="ebf3f-527">Street</span></span>          | <span data-ttu-id="ebf3f-528">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="ebf3f-528">Address Line 1</span></span>        |

### <a name="tax-regions"></a><span data-ttu-id="ebf3f-529">Regiony podatkowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-529">Tax regions</span></span>

<span data-ttu-id="ebf3f-530">Regiony podatkowe służą do określania odpowiedniej stawki podatkowej stosowanej podczas generowania listy płac.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-530">Tax regions are used to determine the appropriate tax that should be applied during payroll generation.</span></span> <span data-ttu-id="ebf3f-531">Regiony podatkowe są mapowane do systemu Dayforce jako adresy lokalizacji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-531">Tax regions are mapped to Dayforce as location addresses.</span></span> <span data-ttu-id="ebf3f-532">Domyślny region podatkowy musi być skojarzony z aktywnym stanowiskiem pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-532">The default tax region must be associated with the worker's active position.</span></span> 

- <span data-ttu-id="ebf3f-533">Region podatkowy (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-533">Tax region (required)</span></span>
- <span data-ttu-id="ebf3f-534">Kraj/region (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-534">Country/Region (required)</span></span>
- <span data-ttu-id="ebf3f-535">Województwo (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-535">State (required)</span></span>
- <span data-ttu-id="ebf3f-536">Powiat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-536">County</span></span> 
- <span data-ttu-id="ebf3f-537">Miejscowość (wymagane)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-537">City (required)</span></span>

## <a name="configure-your-data-to-generate-payroll-in-mexico"></a><span data-ttu-id="ebf3f-538">Konfigurowanie danych w celu generowania listy płac w Meksyku</span><span class="sxs-lookup"><span data-stu-id="ebf3f-538">Configure your data to generate payroll in Mexico</span></span>

<span data-ttu-id="ebf3f-539">Jeśli generujesz płace dla pracowników na terenie Meksyku, należy skonfigurować następujące elementy:</span><span class="sxs-lookup"><span data-stu-id="ebf3f-539">If you're generating pay for employees in Mexico, the following elements must be configured:</span></span>

- <span data-ttu-id="ebf3f-540">Dla stanowisk muszą być określone działy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-540">Departments are required on positions.</span></span>
- <span data-ttu-id="ebf3f-541">Centra kosztów muszą być ustawione jako wymiary finansowe i muszą być pierwszym elementem w ciągu domyślnych wymiarów finansowych.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-541">Cost centers must be set as financial dimensions and must be the first element in the Default Financial Dimension string.</span></span>

### <a name="job-types"></a><span data-ttu-id="ebf3f-542">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="ebf3f-542">Job types</span></span>

<span data-ttu-id="ebf3f-543">Typy funkcji służą do grupowanie podobnych funkcji w kategorie.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-543">Job types are used to group similar jobs into categories.</span></span> <span data-ttu-id="ebf3f-544">Typy funkcji są wymagane w celu przetwarzania listy płac w Meksyku.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-544">Job types are required in order to process payroll in Mexico.</span></span> <span data-ttu-id="ebf3f-545">Przykłady typów funkcji to zatrudnienie w pełnym i niepełnym wymiarze czasu albo wynagrodzenie za etat i za godziny.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-545">Examples of job types include full-time and part-time, or salary and hourly pay.</span></span> <span data-ttu-id="ebf3f-546">Typy funkcji są mapowane do systemu Dayforce jako typy płac, które wskazują, czy pracownik jest na stawce godzinowej, czy stałej pensji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-546">Job types are mapped to Dayforce as pay types that indicate whether an employee is hourly or salaried.</span></span>

<span data-ttu-id="ebf3f-547">Następujące typy funkcji i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-547">The following job types and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-548">Typ funkcji</span><span class="sxs-lookup"><span data-stu-id="ebf3f-548">Job type</span></span>   | <span data-ttu-id="ebf3f-549">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-549">Description</span></span> |
|------------|-------------|
| <span data-ttu-id="ebf3f-550">Co godzinę</span><span class="sxs-lookup"><span data-stu-id="ebf3f-550">Hourly</span></span>     | <span data-ttu-id="ebf3f-551">MX Co godzinę</span><span class="sxs-lookup"><span data-stu-id="ebf3f-551">MX Hourly</span></span>   |
| <span data-ttu-id="ebf3f-552">Stała pensja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-552">Salaried</span></span>   | <span data-ttu-id="ebf3f-553">MX Stała pensja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-553">MX Salaried</span></span> |

### <a name="position-types"></a><span data-ttu-id="ebf3f-554">Typy stanowisk</span><span class="sxs-lookup"><span data-stu-id="ebf3f-554">Position types</span></span> 

<span data-ttu-id="ebf3f-555">Typy stanowisk służą do opisywania, czy stanowisko jest w pełnym wymiarze czasu, niepełnym wymiarze czasu lub ma inną konfigurację.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-555">You use position types to describe whether the position is full-time, part-time, or something else.</span></span> <span data-ttu-id="ebf3f-556">Typy stanowisk są mapowane do systemu Dayforce jako klasy płac, które wskazują, czy pracownik jest zatrudniony na pełny etat, czy na część etatu.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-556">Position types are mapped to Dayforce as pay classes that indicate whether an employee is full-time or part-time.</span></span>

<span data-ttu-id="ebf3f-557">Następujące typy stanowisk i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-557">The following position types and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-558">Typ stanowiska</span><span class="sxs-lookup"><span data-stu-id="ebf3f-558">Position type</span></span>   | <span data-ttu-id="ebf3f-559">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-559">Description</span></span>        |
|-----------------|--------------------|
| <span data-ttu-id="ebf3f-560">Pełny etat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-560">Full-time</span></span>       | <span data-ttu-id="ebf3f-561">Pracownik etatowy zatrudniony w pełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-561">Full time employee</span></span> |
| <span data-ttu-id="ebf3f-562">Część etatu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-562">Part-time</span></span>       | <span data-ttu-id="ebf3f-563">Pracownik etatowy zatrudniony w niepełnym wymiarze czasu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-563">Part time employee</span></span> |

### <a name="reason-codes"></a><span data-ttu-id="ebf3f-564">Kody przyczyn</span><span class="sxs-lookup"><span data-stu-id="ebf3f-564">Reason codes</span></span>

<span data-ttu-id="ebf3f-565">Kody przyczyn informują o stanie pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-565">Reason codes provide information about the status of an employee.</span></span> <span data-ttu-id="ebf3f-566">Kody przyczyn są mapowane do systemu Dayforce jako przyczyny stanu, które wskazują powód zmiany stanowiska lub statusu zatrudnienia pracownika.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-566">Reason codes are mapped to Dayforce as status reasons that indicate the reason for changes to an employee's position or employment status.</span></span>

<span data-ttu-id="ebf3f-567">Następujące kody przyczyn i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-567">The following reason codes and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-568">Kod przyczyny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-568">Reason code</span></span>            | <span data-ttu-id="ebf3f-569">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-569">Description</span></span>                    | <span data-ttu-id="ebf3f-570">Odpowiednie scenariusze</span><span class="sxs-lookup"><span data-stu-id="ebf3f-570">Applicable scenarios</span></span> |
|------------------------|--------------------------------|----------------------|
| <span data-ttu-id="ebf3f-571">DEPARTUREBEFOREPAYMENT</span><span class="sxs-lookup"><span data-stu-id="ebf3f-571">DEPARTUREBEFOREPAYMENT</span></span> | <span data-ttu-id="ebf3f-572">Odejście z pracy przed pierwszą wypłatą</span><span class="sxs-lookup"><span data-stu-id="ebf3f-572">Departure before first payroll</span></span> | <span data-ttu-id="ebf3f-573">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-573">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-574">RESIGNATION</span><span class="sxs-lookup"><span data-stu-id="ebf3f-574">RESIGNATION</span></span>            | <span data-ttu-id="ebf3f-575">Rezygnacja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-575">Resignation</span></span>                    | <span data-ttu-id="ebf3f-576">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-576">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-577">PENSION</span><span class="sxs-lookup"><span data-stu-id="ebf3f-577">PENSION</span></span>                | <span data-ttu-id="ebf3f-578">Emerytura</span><span class="sxs-lookup"><span data-stu-id="ebf3f-578">Pension</span></span>                        | <span data-ttu-id="ebf3f-579">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-579">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-580">TERMINATION</span><span class="sxs-lookup"><span data-stu-id="ebf3f-580">TERMINATION</span></span>            | <span data-ttu-id="ebf3f-581">Przerwanie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-581">Termination</span></span>                    | <span data-ttu-id="ebf3f-582">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-582">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-583">RETIREMENT</span><span class="sxs-lookup"><span data-stu-id="ebf3f-583">RETIREMENT</span></span>             | <span data-ttu-id="ebf3f-584">Emerytura</span><span class="sxs-lookup"><span data-stu-id="ebf3f-584">Retirement</span></span>                     | <span data-ttu-id="ebf3f-585">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-585">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-586">ABSENTEE</span><span class="sxs-lookup"><span data-stu-id="ebf3f-586">ABSENTEE</span></span>               | <span data-ttu-id="ebf3f-587">Absencja</span><span class="sxs-lookup"><span data-stu-id="ebf3f-587">Absentee</span></span>                       | <span data-ttu-id="ebf3f-588">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-588">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-589">INNY</span><span class="sxs-lookup"><span data-stu-id="ebf3f-589">OTHER</span></span>                  | <span data-ttu-id="ebf3f-590">Inne przyczyny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-590">Other Reasons</span></span>                  | <span data-ttu-id="ebf3f-591">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-591">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-592">CLOSURE</span><span class="sxs-lookup"><span data-stu-id="ebf3f-592">CLOSURE</span></span>                | <span data-ttu-id="ebf3f-593">Zaprzestanie działalności przez firmę</span><span class="sxs-lookup"><span data-stu-id="ebf3f-593">Business Closure</span></span>               | <span data-ttu-id="ebf3f-594">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-594">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-595">DEATH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-595">DEATH</span></span>                  | <span data-ttu-id="ebf3f-596">Śmierć</span><span class="sxs-lookup"><span data-stu-id="ebf3f-596">Death</span></span>                          | <span data-ttu-id="ebf3f-597">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-597">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-598">LEAVEOFABSENCE</span><span class="sxs-lookup"><span data-stu-id="ebf3f-598">LEAVEOFABSENCE</span></span>         | <span data-ttu-id="ebf3f-599">Nieobecność</span><span class="sxs-lookup"><span data-stu-id="ebf3f-599">Leave of Absence</span></span>               | <span data-ttu-id="ebf3f-600">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-600">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-601">CONTRACTEND</span><span class="sxs-lookup"><span data-stu-id="ebf3f-601">CONTRACTEND</span></span>            | <span data-ttu-id="ebf3f-602">Zakończenie umowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-602">End of Contract</span></span>                | <span data-ttu-id="ebf3f-603">Zwalnianie pracownika</span><span class="sxs-lookup"><span data-stu-id="ebf3f-603">Terminate worker</span></span>     |
| <span data-ttu-id="ebf3f-604">SALARYCHANGE</span><span class="sxs-lookup"><span data-stu-id="ebf3f-604">SALARYCHANGE</span></span>           | <span data-ttu-id="ebf3f-605">Zmiana wynagrodzenia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-605">Change of Salary</span></span>               | <span data-ttu-id="ebf3f-606">Wynagrodzenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-606">Compensation</span></span>         |

### <a name="terms-of-employment"></a><span data-ttu-id="ebf3f-607">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-607">Terms of employment</span></span>

<span data-ttu-id="ebf3f-608">Warunki zatrudnienia służą do tworzenia kategorii warunków zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-608">Terms of employment are used to create categories of employment terms.</span></span> <span data-ttu-id="ebf3f-609">Warunki są mapowane do systemu Dayforce jako wartości wskaźnika zatrudnienia.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-609">The terms are mapped to Dayforce as employment indicator values.</span></span>

<span data-ttu-id="ebf3f-610">Następujące warunki zatrudnienia i opisy są wymagane.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-610">The following terms of employment and descriptions are required.</span></span>

| <span data-ttu-id="ebf3f-611">Warunki zatrudnienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-611">Terms of employment</span></span>   | <span data-ttu-id="ebf3f-612">opis</span><span class="sxs-lookup"><span data-stu-id="ebf3f-612">Description</span></span> |
|-----------------------|-------------|
| <span data-ttu-id="ebf3f-613">Normalna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-613">Regular</span></span>               | <span data-ttu-id="ebf3f-614">Normalna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-614">Regular</span></span>     |
| <span data-ttu-id="ebf3f-615">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="ebf3f-615">Direct</span></span>                | <span data-ttu-id="ebf3f-616">Bezpośredni</span><span class="sxs-lookup"><span data-stu-id="ebf3f-616">Direct</span></span>      |
| <span data-ttu-id="ebf3f-617">Staż</span><span class="sxs-lookup"><span data-stu-id="ebf3f-617">Internship</span></span>            | <span data-ttu-id="ebf3f-618">Staż</span><span class="sxs-lookup"><span data-stu-id="ebf3f-618">Internship</span></span>  |
| <span data-ttu-id="ebf3f-619">Stałe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-619">Permanent</span></span>             | <span data-ttu-id="ebf3f-620">Stałe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-620">Permanent</span></span>   |

### <a name="marital-status"></a><span data-ttu-id="ebf3f-621">Stan cywilny</span><span class="sxs-lookup"><span data-stu-id="ebf3f-621">Marital status</span></span>

<span data-ttu-id="ebf3f-622">Wartości stanu cywilnego są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-622">Marital status values are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ebf3f-623">W poniższej tabeli przedstawiono mapowanie wartości stanu cywilnego do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-623">The following table shows how marital status values are mapped to Dayforce.</span></span>

| <span data-ttu-id="ebf3f-624">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-624">Talent</span></span>                 | <span data-ttu-id="ebf3f-625">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-625">Dayforce</span></span>                  |
|------------------------|---------------------------|
| <span data-ttu-id="ebf3f-626">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="ebf3f-626">Married</span></span>                | <span data-ttu-id="ebf3f-627">Żonaty/mężatka</span><span class="sxs-lookup"><span data-stu-id="ebf3f-627">Married</span></span>                   |
| <span data-ttu-id="ebf3f-628">Jedno</span><span class="sxs-lookup"><span data-stu-id="ebf3f-628">Single</span></span>                 | <span data-ttu-id="ebf3f-629">Jedno</span><span class="sxs-lookup"><span data-stu-id="ebf3f-629">Single</span></span>                    |
| <span data-ttu-id="ebf3f-630">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-630">Widowed</span></span>                | <span data-ttu-id="ebf3f-631">Wdowiec/wdowa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-631">Widowed</span></span>                   |
| <span data-ttu-id="ebf3f-632">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="ebf3f-632">Divorced</span></span>               | <span data-ttu-id="ebf3f-633">Rozwiedziony/rozwiedziona</span><span class="sxs-lookup"><span data-stu-id="ebf3f-633">Divorced</span></span>                  |
| <span data-ttu-id="ebf3f-634">Związek zarejestrowany</span><span class="sxs-lookup"><span data-stu-id="ebf3f-634">Registered Partnership</span></span> | <span data-ttu-id="ebf3f-635">Partnerstwo krajowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-635">Domestic Partnership</span></span>      |
| <span data-ttu-id="ebf3f-636">None</span><span class="sxs-lookup"><span data-stu-id="ebf3f-636">None</span></span>                   | <span data-ttu-id="ebf3f-637">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-637">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ebf3f-638">Konkubinat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-638">Cohabiting</span></span>             | <span data-ttu-id="ebf3f-639">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-639">*Not supported by Mexico*</span></span> |

### <a name="gender"></a><span data-ttu-id="ebf3f-640">Rodzaj</span><span class="sxs-lookup"><span data-stu-id="ebf3f-640">Gender</span></span>

<span data-ttu-id="ebf3f-641">Określenia płci są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-641">Gender designations are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ebf3f-642">W poniższej tabeli przedstawiono mapowanie określeń płci do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-642">The following table shows how gender designations are mapped to Dayforce.</span></span>

| <span data-ttu-id="ebf3f-643">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-643">Talent</span></span>       | <span data-ttu-id="ebf3f-644">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-644">Dayforce</span></span>                  |
|--------------|---------------------------|
| <span data-ttu-id="ebf3f-645">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-645">Male</span></span>         | <span data-ttu-id="ebf3f-646">Mężczyzna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-646">Male</span></span>                      |
| <span data-ttu-id="ebf3f-647">Kobieta</span><span class="sxs-lookup"><span data-stu-id="ebf3f-647">Female</span></span>       | <span data-ttu-id="ebf3f-648">Kobieta</span><span class="sxs-lookup"><span data-stu-id="ebf3f-648">Female</span></span>                    |
| <span data-ttu-id="ebf3f-649">Nieokreślone</span><span class="sxs-lookup"><span data-stu-id="ebf3f-649">Non-specific</span></span> | <span data-ttu-id="ebf3f-650">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-650">*Not supported by Mexico*</span></span> |

### <a name="payment-method"></a><span data-ttu-id="ebf3f-651">Metoda płatności</span><span class="sxs-lookup"><span data-stu-id="ebf3f-651">Payment method</span></span>

<span data-ttu-id="ebf3f-652">Funkcja metod płatności oferuje pracownikowi i firmie sposób opisania, jak pracownik będzie otrzymywał zapłatę.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-652">Payment methods give the employee and the company a way to describe how employees will be paid.</span></span> <span data-ttu-id="ebf3f-653">Metody płatności są mapowane do systemu Dayforce i w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-653">Payment methods are mapped to Dayforce and translated, as appropriate, to the accepted values upon integration.</span></span>

<span data-ttu-id="ebf3f-654">W poniższej tabeli przedstawiono mapowanie metod płatności do usługi Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-654">The following table shows how payment methods are mapped to Dayforce.</span></span>

| <span data-ttu-id="ebf3f-655">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-655">Talent</span></span>             | <span data-ttu-id="ebf3f-656">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-656">Dayforce</span></span>                  |
|--------------------|---------------------------|
| <span data-ttu-id="ebf3f-657">Kasa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-657">Cash</span></span>               | <span data-ttu-id="ebf3f-658">Kasa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-658">Cash</span></span>                      |
| <span data-ttu-id="ebf3f-659">Płatność elektroniczna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-659">Electronic Payment</span></span> | <span data-ttu-id="ebf3f-660">Przenoszenie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-660">Transfer</span></span>                  |
| <span data-ttu-id="ebf3f-661">Sprawdzanie</span><span class="sxs-lookup"><span data-stu-id="ebf3f-661">Check</span></span>              | <span data-ttu-id="ebf3f-662">Czek</span><span class="sxs-lookup"><span data-stu-id="ebf3f-662">Cheque</span></span>                    |
| <span data-ttu-id="ebf3f-663">Przekaz bankowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-663">Bank Draft</span></span>         | <span data-ttu-id="ebf3f-664">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-664">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ebf3f-665">Inna</span><span class="sxs-lookup"><span data-stu-id="ebf3f-665">Other</span></span>              | <span data-ttu-id="ebf3f-666">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-666">*Not supported by Mexico*</span></span> |

### <a name="bank-account-type"></a><span data-ttu-id="ebf3f-667">Typ konta bankowego</span><span class="sxs-lookup"><span data-stu-id="ebf3f-667">Bank account type</span></span>

<span data-ttu-id="ebf3f-668">Typy kont bankowych są wykorzystywane w płatnościach elektronicznych dla pracowników.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-668">Bank account types are used for electronic payments to employees.</span></span> <span data-ttu-id="ebf3f-669">Typy kont bankowych są mapowane do systemu Dayforce jako informacje o koncie do przelewów.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-669">Bank account types are mapped to Dayforce as transfer account information.</span></span> <span data-ttu-id="ebf3f-670">Typy kont bankowych są w razie potrzeby tłumaczone na akceptowane wartości podczas integracji.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-670">The bank account types are translated, as appropriate, to the accepted values upon integration.</span></span>

| <span data-ttu-id="ebf3f-671">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-671">Talent</span></span>            | <span data-ttu-id="ebf3f-672">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-672">Dayforce</span></span>                  |
|-------------------|---------------------------|
| <span data-ttu-id="ebf3f-673">Konto czekowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-673">Checking Account</span></span>  | <span data-ttu-id="ebf3f-674">CheckingAccount</span><span class="sxs-lookup"><span data-stu-id="ebf3f-674">CheckingAccount</span></span>           |
| <span data-ttu-id="ebf3f-675">Konto listy płac</span><span class="sxs-lookup"><span data-stu-id="ebf3f-675">Payroll Account</span></span>   | <span data-ttu-id="ebf3f-676">PayrollAccount</span><span class="sxs-lookup"><span data-stu-id="ebf3f-676">PayrollAccount</span></span>            |
| <span data-ttu-id="ebf3f-677">Konto oszczędnościowe</span><span class="sxs-lookup"><span data-stu-id="ebf3f-677">Savings Account</span></span>   | <span data-ttu-id="ebf3f-678">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-678">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ebf3f-679">Konto BankGirot</span><span class="sxs-lookup"><span data-stu-id="ebf3f-679">BankGirot account</span></span> | <span data-ttu-id="ebf3f-680">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-680">*Not supported by Mexico*</span></span> |
| <span data-ttu-id="ebf3f-681">Konto PlusGirot</span><span class="sxs-lookup"><span data-stu-id="ebf3f-681">PlusGirot account</span></span> | <span data-ttu-id="ebf3f-682">*Nieobsługiwane w Meksyku*</span><span class="sxs-lookup"><span data-stu-id="ebf3f-682">*Not supported by Mexico*</span></span> |

### <a name="earning-codes"></a><span data-ttu-id="ebf3f-683">Kody zarobków</span><span class="sxs-lookup"><span data-stu-id="ebf3f-683">Earning codes</span></span>

<span data-ttu-id="ebf3f-684">Kody zarobków jednoznacznie identyfikują każdy rodzaj dochodów, które otrzymują pracownicy.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-684">Earning codes uniquely identify every type of earnings that workers receive.</span></span> <span data-ttu-id="ebf3f-685">Kody mają różne parametry związane z zarobkami, takie jak reguły księgowania, przepisy podatkowe, wymagania dotyczące raportowania i możliwość zwiększania wartości brutto.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-685">The codes cover several parameters that are related to earnings, such as accounting rules, tax laws, reporting requirements, and gross-up capability.</span></span> <span data-ttu-id="ebf3f-686">W razie ustawienia nieobsługiwanej częstotliwości domyślnie w obliczeniu będzie używana częstotliwość **Każda wypłata**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-686">If an unsupported frequency is used, the **Every Pay** frequency is used by default for the calculation.</span></span>

#### <a name="supported-frequencies"></a><span data-ttu-id="ebf3f-687">Obsługiwane częstotliwości</span><span class="sxs-lookup"><span data-stu-id="ebf3f-687">Supported frequencies</span></span>

- <span data-ttu-id="ebf3f-688">Wszyscy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-688">All</span></span>
- <span data-ttu-id="ebf3f-689">EVERYPAY</span><span class="sxs-lookup"><span data-stu-id="ebf3f-689">EVERYPAY</span></span>
- <span data-ttu-id="ebf3f-690">EACHPAYPERIOD</span><span class="sxs-lookup"><span data-stu-id="ebf3f-690">EACHPAYPERIOD</span></span>
- <span data-ttu-id="ebf3f-691">EVRYOTHRPAYODD</span><span class="sxs-lookup"><span data-stu-id="ebf3f-691">EVRYOTHRPAYODD</span></span>
- <span data-ttu-id="ebf3f-692">EVRYOTHRPAYEVN</span><span class="sxs-lookup"><span data-stu-id="ebf3f-692">EVRYOTHRPAYEVN</span></span>
- <span data-ttu-id="ebf3f-693">1OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-693">1OFMTH</span></span>
- <span data-ttu-id="ebf3f-694">LASTOFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-694">LASTOFMTH</span></span>
- <span data-ttu-id="ebf3f-695">2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-695">2OFMTH</span></span>
- <span data-ttu-id="ebf3f-696">3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-696">3OFMTH</span></span>
- <span data-ttu-id="ebf3f-697">4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-697">4OFMTH</span></span>
- <span data-ttu-id="ebf3f-698">5OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-698">5OFMTH</span></span>
- <span data-ttu-id="ebf3f-699">1N2OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-699">1N2OFMTH</span></span>
- <span data-ttu-id="ebf3f-700">3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-700">3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-701">1N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-701">1N3OFMTH</span></span>
- <span data-ttu-id="ebf3f-702">1N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-702">1N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-703">2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-703">2N3OFMTH</span></span>
- <span data-ttu-id="ebf3f-704">2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-704">2N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-705">1N2N3OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-705">1N2N3OFMTH</span></span>
- <span data-ttu-id="ebf3f-706">1N2N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-706">1N2N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-707">1N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-707">1N3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-708">2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-708">2N3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-709">1N2N3N4OFMTH – 1N2N3N4OFMTH</span><span class="sxs-lookup"><span data-stu-id="ebf3f-709">1N2N3N4OFMTH - 1N2N3N4OFMTH</span></span>
- <span data-ttu-id="ebf3f-710">2N3N4N5OFMth – 2N3N4N5OFMth</span><span class="sxs-lookup"><span data-stu-id="ebf3f-710">2N3N4N5OFMth - 2N3N4N5OFMth</span></span>
- <span data-ttu-id="ebf3f-711">1OFQTR – 1OFQTR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-711">1OFQTR - 1OFQTR</span></span>
- <span data-ttu-id="ebf3f-712">LASTOFQTR – LASTOFQTR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-712">LASTOFQTR – LASTOFQTR</span></span>
- <span data-ttu-id="ebf3f-713">LASTMTHOFQTR – LASTMTHOFQTR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-713">LASTMTHOFQTR – LASTMTHOFQTR</span></span>
- <span data-ttu-id="ebf3f-714">1OFYEAR – 1OFYEAR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-714">1OFYEAR - 1OFYEAR</span></span>
- <span data-ttu-id="ebf3f-715">LASTOFYEAR – LASTOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-715">LASTOFYEAR – LASTOFYEAR</span></span>
- <span data-ttu-id="ebf3f-716">NOVNDECOFYEAR – NOVNDECOFYEAR</span><span class="sxs-lookup"><span data-stu-id="ebf3f-716">NOVNDECOFYEAR - NOVNDECOFYEAR</span></span>

### <a name="addresses"></a><span data-ttu-id="ebf3f-717">Adresy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-717">Addresses</span></span>

<span data-ttu-id="ebf3f-718">Identyfikacja określonych kodów kraju lub regionu, województwa i powiatu (gminy) wymaga określonych formatów, które potrafi rozpoznać system Dayforce oraz dostawcy wewnątrz krajów/regionów.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-718">The identification of specific country or region, state, and county (municipality) codes requires specific formats that Dayforce and in-country/in-region providers can recognize.</span></span> <span data-ttu-id="ebf3f-719">Co prawda format nazw miejscowości jest elastyczny, ale każda miejscowość musi być skojarzona z województwem.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-719">Although the format for cities is flexible, every city must be associated with a state.</span></span>

| <span data-ttu-id="ebf3f-720">Talent</span><span class="sxs-lookup"><span data-stu-id="ebf3f-720">Talent</span></span>              | <span data-ttu-id="ebf3f-721">Dayforce</span><span class="sxs-lookup"><span data-stu-id="ebf3f-721">Dayforce</span></span>              |
|---------------------|-----------------------|
| <span data-ttu-id="ebf3f-722">Kraj/region</span><span class="sxs-lookup"><span data-stu-id="ebf3f-722">Country/Region</span></span>      | <span data-ttu-id="ebf3f-723">Kod kraju</span><span class="sxs-lookup"><span data-stu-id="ebf3f-723">Country Code</span></span>          |
| <span data-ttu-id="ebf3f-724">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-724">Zip/Postal Code</span></span>     | <span data-ttu-id="ebf3f-725">Kod pocztowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-725">Postal Code</span></span>           |
| <span data-ttu-id="ebf3f-726">Stanowy</span><span class="sxs-lookup"><span data-stu-id="ebf3f-726">State</span></span>               | <span data-ttu-id="ebf3f-727">Kod województwa</span><span class="sxs-lookup"><span data-stu-id="ebf3f-727">State Code</span></span>            |
| <span data-ttu-id="ebf3f-728">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="ebf3f-728">City</span></span>                | <span data-ttu-id="ebf3f-729">Miejscowość</span><span class="sxs-lookup"><span data-stu-id="ebf3f-729">City</span></span>                  |
| <span data-ttu-id="ebf3f-730">Powiat</span><span class="sxs-lookup"><span data-stu-id="ebf3f-730">County</span></span>              | <span data-ttu-id="ebf3f-731">Powiat (gmina)</span><span class="sxs-lookup"><span data-stu-id="ebf3f-731">County (Municipality)</span></span> |
| <span data-ttu-id="ebf3f-732">Ulica</span><span class="sxs-lookup"><span data-stu-id="ebf3f-732">Street</span></span>              | <span data-ttu-id="ebf3f-733">Wiersz adresu 1</span><span class="sxs-lookup"><span data-stu-id="ebf3f-733">Address Line 1</span></span>        |
| <span data-ttu-id="ebf3f-734">Numer budynku</span><span class="sxs-lookup"><span data-stu-id="ebf3f-734">Street Number</span></span>       | <span data-ttu-id="ebf3f-735">Wiersz adresu 2</span><span class="sxs-lookup"><span data-stu-id="ebf3f-735">Address Line 2</span></span>        |
| <span data-ttu-id="ebf3f-736">Dodatkowe określenie budynku</span><span class="sxs-lookup"><span data-stu-id="ebf3f-736">Building Complement</span></span> | <span data-ttu-id="ebf3f-737">Wiersz adresu 5</span><span class="sxs-lookup"><span data-stu-id="ebf3f-737">Address Line 5</span></span>        |

### <a name="passport-number"></a><span data-ttu-id="ebf3f-738">Numer paszportu</span><span class="sxs-lookup"><span data-stu-id="ebf3f-738">Passport number</span></span>

<span data-ttu-id="ebf3f-739">Pracownicy mogą podać informacje z paszportów.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-739">Employees can declare passport information.</span></span> <span data-ttu-id="ebf3f-740">Te informacje mają typ identyfikacji **Paszport** i są integrowane z systemem Dayforce w ramach danych pracowników specyficznych dla Meksyku.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-740">This information is of the **Passport** identification type and is integrated into Dayforce as part of an employee's Mexico-specific information.</span></span>

- <span data-ttu-id="ebf3f-741">Typ identyfikacji = „Paszport”</span><span class="sxs-lookup"><span data-stu-id="ebf3f-741">Identification Type = "Passport"</span></span>
- <span data-ttu-id="ebf3f-742">Data wystawienia</span><span class="sxs-lookup"><span data-stu-id="ebf3f-742">Issued Date</span></span>
- <span data-ttu-id="ebf3f-743">Data ważności</span><span class="sxs-lookup"><span data-stu-id="ebf3f-743">Expiration Date</span></span>

<span data-ttu-id="ebf3f-744">Pracownicy mogą zadeklarować wiele numerów identyfikacyjnych typu **Paszport**.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-744">Employees can declare multiple identification numbers of the **Passport** identification type.</span></span> <span data-ttu-id="ebf3f-745">Jednak tylko obecnie aktywny wpis paszportu jest integrowany z usługą Dayforce.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-745">However, only the current active passport entry is integrated into Dayforce.</span></span> <span data-ttu-id="ebf3f-746">Jeśli wszystkie wpisy paszportów wygasły, z systemem Dayforce zostanie zintegrowany ostatnio wystawiony paszport.</span><span class="sxs-lookup"><span data-stu-id="ebf3f-746">If all passport entries are expired, the passport that was most recently issued is integrated into Dayforce.</span></span>
