---
title: "Integracja fiskalna dla kanału detalicznego"
description: "W tym temacie zawarto ogólne informacje o integracji fiskalnej w aplikacji Retail POS."
author: josaw
manager: annbe
ms.date: 11/01/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailFunctionalityProfile, RetailFormLayout, RetailParameters
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.search.region: Global
ms.search.industry: Retail
ms.author: v-kikozl
ms.search.validFrom: 2018-11-1
ms.dyn365.ops.version: 8.1.1
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: c852d095505abecbd44d29e9e7b53875e9069def
ms.contentlocale: pl-pl
ms.lasthandoff: 11/01/2018

---
# <a name="fiscal-integration-for-retail-channel"></a><span data-ttu-id="702cb-103">Integracja fiskalna dla kanału detalicznego</span><span class="sxs-lookup"><span data-stu-id="702cb-103">Fiscal integration for Retail channel</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="702cb-104">W tym temacie przedstawiono omówienie funkcji integracji fiskalnej dostępnych w aplikacji Microsoft Dynamics 365 for Retail.</span><span class="sxs-lookup"><span data-stu-id="702cb-104">This topic is an overview of the fiscal integration functionality that is available in Microsoft Dynamics 365 for Retail.</span></span> <span data-ttu-id="702cb-105">Funkcjonalność integracji fiskalnej to struktura zapewniająca obsługę lokalnych przepisów podatkowych, które mają na celu zapobieganie nadużyciom finansowym w branży handlu detalicznego.</span><span class="sxs-lookup"><span data-stu-id="702cb-105">The fiscal integration functionality is a framework designed to support local fiscal laws that are aimed to prevent fraud in the Retail industry.</span></span> <span data-ttu-id="702cb-106">Oto kilka typowych scenariuszy wykorzystania funkcji integracji fiskalnej:</span><span class="sxs-lookup"><span data-stu-id="702cb-106">Typical scenarios that could be covered by using fiscal integration include:</span></span>

- <span data-ttu-id="702cb-107">Wydrukowanie paragonu fiskalnego i wręczenie go klientowi.</span><span class="sxs-lookup"><span data-stu-id="702cb-107">Printing a fiscal receipt and giving it to the customer.</span></span>
- <span data-ttu-id="702cb-108">Zabezpieczenie przesyłania informacji o sprzedaży i zwrotach dokonanych w punkcie sprzedaży do zewnętrznego systemu urzędowego.</span><span class="sxs-lookup"><span data-stu-id="702cb-108">Securing the submission of the information related to sales and returns performed on POS to an external service provided by the authority.</span></span>
- <span data-ttu-id="702cb-109">Stosowanie mechanizmu ochrony danych z podpisami cyfrowymi autoryzowanymi przez urząd.</span><span class="sxs-lookup"><span data-stu-id="702cb-109">Using data protection with a digital signature authorized by the authority.</span></span>

<span data-ttu-id="702cb-110">W tym temacie zawarto wytyczne dotyczące konfigurowania funkcji integracji fiskalnej, tak aby użytkownicy mogli wykonywać następujące zadania.</span><span class="sxs-lookup"><span data-stu-id="702cb-110">This topic provides guidelines for setting up fiscal integration so users can perform the following tasks.</span></span> 

- <span data-ttu-id="702cb-111">Konfigurowanie łączników fiskalnych, czyli urządzeń lub usług fiskalnych używanych do celów rejestracji fiskalnej, takich jak operacje zapisywania, składania podpisów cyfrowych i bezpiecznego przesyłania danych fiskalnych.</span><span class="sxs-lookup"><span data-stu-id="702cb-111">Configure fiscal connectors, which are fiscal devices or services used for fiscal registration purposes like saving, digital signatures, and secured submission of fiscal data.</span></span>
- <span data-ttu-id="702cb-112">Konfigurowanie dostawcy dokumentów, który określa metodę wyprowadzania danych oraz algorytm generowania dokumentów fiskalnych.</span><span class="sxs-lookup"><span data-stu-id="702cb-112">Configure the document provider, which defines an output method and an algorithm of fiscal document generation.</span></span>
- <span data-ttu-id="702cb-113">Konfigurowanie procesu rejestracji fiskalnej, który określa kolejność etapów oraz grupę łączników używanych na każdym etapie.</span><span class="sxs-lookup"><span data-stu-id="702cb-113">Configure the fiscal registration process, which is defines a sequence of steps and a group of connectors used on each step.</span></span>
- <span data-ttu-id="702cb-114">Przypisywanie procesów rejestracji fiskalnej do profili funkcji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="702cb-114">Assign fiscal registration processes to POS functionality profiles.</span></span>
- <span data-ttu-id="702cb-115">Przypisywanie profili technicznych łączników do profili sprzętowych (w przypadku lokalnych łączników fiskalnych) lub profili funkcji punktu sprzedaży (w przypadku innych typów łączników fiskalnych).</span><span class="sxs-lookup"><span data-stu-id="702cb-115">Assign connector technical profiles, either to hardware profiles (for the local fiscal connectors) or to POS functionality profiles (for other fiscal connector types).</span></span>

## <a name="fiscal-integration-execution-flow"></a><span data-ttu-id="702cb-116">Proces tworzenia integracji finansowej</span><span class="sxs-lookup"><span data-stu-id="702cb-116">Fiscal integration execution flow</span></span>
<span data-ttu-id="702cb-117">Poniższy scenariusz pokazuje typowy proces tworzenia integracji finansowej.</span><span class="sxs-lookup"><span data-stu-id="702cb-117">The following scenario shows the common fiscal integration execution flow.</span></span>

1. <span data-ttu-id="702cb-118">Zainicjowanie procesu rejestracji fiskalnej.</span><span class="sxs-lookup"><span data-stu-id="702cb-118">Initialization of the fiscal registration process.</span></span>
  
   <span data-ttu-id="702cb-119">Po wykonaniu pewnych czynności, w których jest wymagana rejestracja fiskalna, na przykład po zawarciu transakcji sprzedaży detalicznej, proces rejestracji fiskalnej jest kojarzony z bieżącym profilem funkcji punktu sprzedaży.</span><span class="sxs-lookup"><span data-stu-id="702cb-119">After performing some actions where fiscal registration is required, such as after a retail transaction has been concluded, the fiscal registration process is associated with the current POS functionality profile.</span></span>

1. <span data-ttu-id="702cb-120">Wyszukanie łącznika fiskalnego.</span><span class="sxs-lookup"><span data-stu-id="702cb-120">Search for a fiscal connector.</span></span>
   
   <span data-ttu-id="702cb-121">Dla każdego etapu rejestracji fiskalnej w procesie rejestracji fiskalnej system znajduje pasujące łączniki fiskalne podane na liście.</span><span class="sxs-lookup"><span data-stu-id="702cb-121">For each fiscal registration step included in the fiscal registration process, the system matches the list of fiscal connectors.</span></span> <span data-ttu-id="702cb-122">Te łączniki mają profile funkcjonalności należące do podanej grupy łączników z listą łączników, które mają profile techniczne skojarzone z bieżącym profilem sprzętowym (tylko dla typu łącznika **Lokalny**) lub z bieżącym profilem funkcji punktu sprzedaży (dla innych typów łączników).</span><span class="sxs-lookup"><span data-stu-id="702cb-122">These connectors have a functional profile included in the specified connector group, with a list of connectors that have a technical profile associated with the current hardware profile (for a connector type that equals **Local** only) or with the current POS functionality profile (for other connector types).</span></span>
   
1. <span data-ttu-id="702cb-123">Wykonanie integracji fiskalnej.</span><span class="sxs-lookup"><span data-stu-id="702cb-123">Perform the fiscal integration.</span></span>

   <span data-ttu-id="702cb-124">System wykonuje wszystkie niezbędne czynności zdefiniowane przez zestaw połączony ze znalezionym łącznikiem.</span><span class="sxs-lookup"><span data-stu-id="702cb-124">The system executes all necessary actions defined by an assembly linked with the found connector.</span></span> <span data-ttu-id="702cb-125">Odbywa się to zgodnie z ustawieniami profilu funkcjonalności i profilu technicznego znalezionymi na poprzednim etapie dla tego łącznika.</span><span class="sxs-lookup"><span data-stu-id="702cb-125">This is done in accordance with the settings of the functional profile and technical profile that were found on the previous step for this connector.</span></span>

## <a name="setup-needed-before-using-fiscal-integration"></a><span data-ttu-id="702cb-126">Konfiguracja wymagana przed wykonaniem integracji fiskalnej</span><span class="sxs-lookup"><span data-stu-id="702cb-126">Setup needed before using fiscal integration</span></span>
<span data-ttu-id="702cb-127">Przed użyciem funkcji integracji fiskalnej należy zdefiniować następujące ustawienia:</span><span class="sxs-lookup"><span data-stu-id="702cb-127">Before using the fiscal integration functionality, you should define the following settings:</span></span>

- <span data-ttu-id="702cb-128">Zdefiniuj numerację na stronie **Parametry sieci sprzedaży** dla fiskalnego profilu funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="702cb-128">Define the number sequence on the **Retail parameters** page for the fiscal functional profile number.</span></span>
  
- <span data-ttu-id="702cb-129">Określ numeracje na stronie **Wspólne parametry sieci sprzedaży** dla następujących odwołań:</span><span class="sxs-lookup"><span data-stu-id="702cb-129">Define the number sequences on the **Retail shared parameters** page for the following references:</span></span>
  
  - <span data-ttu-id="702cb-130">Identyfikator fiskalnego profilu technicznego</span><span class="sxs-lookup"><span data-stu-id="702cb-130">Fiscal technical profile number</span></span>
  - <span data-ttu-id="702cb-131">Identyfikator grupy łącznika fiskalnego</span><span class="sxs-lookup"><span data-stu-id="702cb-131">Fiscal connector group number</span></span>
  - <span data-ttu-id="702cb-132">Identyfikator procesu rejestracji</span><span class="sxs-lookup"><span data-stu-id="702cb-132">Registration process number</span></span>

- <span data-ttu-id="702cb-133">Utwórz **łącznik fiskalny** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Łączniki fiskalne** dla każdego urządzenia lub usługi, których planujesz używać na potrzeby integracji fiskalnej.</span><span class="sxs-lookup"><span data-stu-id="702cb-133">Create a **Fiscal connector** in **Retail > Channel setup > Fiscal integration > Fiscal connectors** for each device or service that you plan to use for fiscal integration purposes.</span></span>

-  <span data-ttu-id="702cb-134">Utwórz **dostawcę dokumentów fiskalnych** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Dostawcy dokumentów fiskalnych** dla wszystkich łączników fiskalnych.</span><span class="sxs-lookup"><span data-stu-id="702cb-134">Create a **Fiscal document provider** in **Retail > Channel setup > Fiscal integration > Fiscal document providers** for all fiscal connectors.</span></span> <span data-ttu-id="702cb-135">Mapowanie danych jest uważane za element dostawcy dokumentów fiskalnych.</span><span class="sxs-lookup"><span data-stu-id="702cb-135">Data mapping is considered a part of the fiscal document provider.</span></span> <span data-ttu-id="702cb-136">Aby skonfigurować inne mapowania danych dla tego samego łącznika (np. do obsługi szczególnych przepisów stanowych), należy utworzyć innych dostawców dokumentów fiskalnych.</span><span class="sxs-lookup"><span data-stu-id="702cb-136">To set up different data mappings for the same connector (like state-specific regulations), you should create different fiscal document providers.</span></span>

- <span data-ttu-id="702cb-137">Utwórz **profil funkcjonalności łącznika** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Profile funkcjonalności łącznika** dla każdego dostawcy dokumentów fiskalnych.</span><span class="sxs-lookup"><span data-stu-id="702cb-137">Create a **Connector functional profile** in **Retail > Channel setup > Fiscal integration > Connector functional profiles** for each fiscal document provider.</span></span>
  - <span data-ttu-id="702cb-138">Nazwij łącznik.</span><span class="sxs-lookup"><span data-stu-id="702cb-138">Select a connector name.</span></span>
  - <span data-ttu-id="702cb-139">Wybierz dostawcę dokumentów.</span><span class="sxs-lookup"><span data-stu-id="702cb-139">Select a document provider.</span></span>
  - <span data-ttu-id="702cb-140">Określ ustawienia stawek podatku VAT na karcie **Ustawienia usługi**.</span><span class="sxs-lookup"><span data-stu-id="702cb-140">Specify VAT rates settings on the **Service setup** tab.</span></span>
  - <span data-ttu-id="702cb-141">Określ mapowanie kodów podatku VAT i mapowanie typów metod płatności na karcie **Mapowanie danych**.</span><span class="sxs-lookup"><span data-stu-id="702cb-141">Specify VAT codes mapping and tender type mapping on the **Data mapping** tab.</span></span>

  #### <a name="examples"></a><span data-ttu-id="702cb-142">Przykłady</span><span class="sxs-lookup"><span data-stu-id="702cb-142">Examples</span></span> 

  |  | <span data-ttu-id="702cb-143">Format</span><span class="sxs-lookup"><span data-stu-id="702cb-143">Format</span></span> | <span data-ttu-id="702cb-144">Przykład</span><span class="sxs-lookup"><span data-stu-id="702cb-144">Example</span></span> | 
  |--------|--------|--------|
  | <span data-ttu-id="702cb-145">Ustawienia stawek podatku VAT</span><span class="sxs-lookup"><span data-stu-id="702cb-145">VAT rates settings</span></span> | <span data-ttu-id="702cb-146">wartość : VATrate</span><span class="sxs-lookup"><span data-stu-id="702cb-146">value : VATrate</span></span> | <span data-ttu-id="702cb-147">1 : 2000, 2 : 1800</span><span class="sxs-lookup"><span data-stu-id="702cb-147">1 : 2000, 2 : 1800</span></span> |
  | <span data-ttu-id="702cb-148">Mapowanie kodów VAT</span><span class="sxs-lookup"><span data-stu-id="702cb-148">VAT codes mapping</span></span> | <span data-ttu-id="702cb-149">VATcode : wartość</span><span class="sxs-lookup"><span data-stu-id="702cb-149">VATcode : value</span></span> | <span data-ttu-id="702cb-150">vat20 : 1, vat18 : 2</span><span class="sxs-lookup"><span data-stu-id="702cb-150">vat20 : 1, vat18 : 2</span></span> |
  | <span data-ttu-id="702cb-151">Mapowanie typów metod płatności</span><span class="sxs-lookup"><span data-stu-id="702cb-151">Tender types mapping</span></span> | <span data-ttu-id="702cb-152">TenderTyp : wartość</span><span class="sxs-lookup"><span data-stu-id="702cb-152">TenderTyp : value</span></span> | <span data-ttu-id="702cb-153">Gotówka : 1, Karta : 2</span><span class="sxs-lookup"><span data-stu-id="702cb-153">Cash : 1, Card : 2</span></span> |

- <span data-ttu-id="702cb-154">Utwórz **grupę łączników fiskalnych** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Grupa łącznika fiskalnego**.</span><span class="sxs-lookup"><span data-stu-id="702cb-154">Create **Fiscal connector groups** in **Retail > Channel setup > Fiscal integration > Fiscal connector group**.</span></span> <span data-ttu-id="702cb-155">Grupa łączników to podzbiór profili funkcjonalności połączonych z łącznikami fiskalnymi, które wykonują te same funkcje i są używane na tym samym etapie procesu rejestracji fiskalnej.</span><span class="sxs-lookup"><span data-stu-id="702cb-155">A connector group is a subset of functional profiles linked with fiscal connectors that perform identical functions and are used at the same stage within a fiscal registration process.</span></span>

   - <span data-ttu-id="702cb-156">Dodaj profile funkcjonalności do grupy łączników.</span><span class="sxs-lookup"><span data-stu-id="702cb-156">Add functional profiles to the connector group.</span></span> <span data-ttu-id="702cb-157">Kliknij przycisk **Dodaj** na stronie **Profile funkcjonalności** i wybierz numer profilu.</span><span class="sxs-lookup"><span data-stu-id="702cb-157">Click **Add** on the **Functional profiles** page and select a profile number.</span></span>
   - <span data-ttu-id="702cb-158">Jeśli chcesz zawiesić używanie profilu funkcjonalności, w ustawieniu **Wyłącz** zaznacz wartość **Tak**.</span><span class="sxs-lookup"><span data-stu-id="702cb-158">If you want to suspend usage of the functional profile, set **Disable** to **Yes**.</span></span> 
   
     <span data-ttu-id="702cb-159">Ta zmiana dotyczy tylko bieżącej grupy łączników.</span><span class="sxs-lookup"><span data-stu-id="702cb-159">This change affects the current connector group only.</span></span> <span data-ttu-id="702cb-160">Możesz kontynuować używanie tego samego profilu funkcjonalności w innych grupach łączników.</span><span class="sxs-lookup"><span data-stu-id="702cb-160">You can continue using the same functional profile in other connector groups.</span></span>

     >[!NOTE]
     > <span data-ttu-id="702cb-161">Wewnątrz grupy łączników każdy łącznik fiskalny może mieć tylko jeden profil funkcjonalności.</span><span class="sxs-lookup"><span data-stu-id="702cb-161">Within a connector group, each fiscal connector can only have one functional profile.</span></span>

- <span data-ttu-id="702cb-162">Utwórz **profil techniczny łącznika** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Profile techniczne łącznika** dla każdego łącznika fiskalnego.</span><span class="sxs-lookup"><span data-stu-id="702cb-162">Create a **Connector technical profile** in **Retail > Channel setup > Fiscal integration > Connector technical profiles** for each fiscal connector.</span></span>
  - <span data-ttu-id="702cb-163">Nazwij łącznik.</span><span class="sxs-lookup"><span data-stu-id="702cb-163">Select a connector name.</span></span>
  - <span data-ttu-id="702cb-164">Wybierz typ łącznika:</span><span class="sxs-lookup"><span data-stu-id="702cb-164">Select a connector type:</span></span> 
      - <span data-ttu-id="702cb-165">**Lokalny** — ustaw ten typ dla fizycznych urządzeń lub aplikacji zainstalowanych na komputerze lokalnym.</span><span class="sxs-lookup"><span data-stu-id="702cb-165">**Local** - Set this type for physical devices or applications installed on a local machine.</span></span>
      - <span data-ttu-id="702cb-166">**Wewnętrzny** — ustaw ten typ dla urządzeń fiskalnych i usług połączonych z aplikacją Retail Server.</span><span class="sxs-lookup"><span data-stu-id="702cb-166">**Internal** - Set this type for fiscal devices and services connected to Retail Server.</span></span>
      - <span data-ttu-id="702cb-167">**Zewnętrzny** — dla zewnętrznych usług obrachunkowych, takich jak portal internetowy udostępniony przez urząd skarbowy.</span><span class="sxs-lookup"><span data-stu-id="702cb-167">**External** - For external fiscal services like a web-portal provided by a tax authority.</span></span>
    
  - <span data-ttu-id="702cb-168">Określ ustawienia na karcie **Połączenie**.</span><span class="sxs-lookup"><span data-stu-id="702cb-168">Specify settings on the **Connection** tab.</span></span>

      
 >[!NOTE]
 > <span data-ttu-id="702cb-169">Dla profili technicznych i funkcjonalności zostanie załadowana zaktualizowana wersja załadowanej wcześniej konfiguracji.</span><span class="sxs-lookup"><span data-stu-id="702cb-169">An updated version of a configuration that was loaded earlier will be loaded for both functional and technical profiles.</span></span> <span data-ttu-id="702cb-170">Jeśli odpowiedni łącznik lub dostawca dokumentów jest już używany, otrzymasz o tym powiadomienie.</span><span class="sxs-lookup"><span data-stu-id="702cb-170">If an appropriate connector or document provider is already in use, you will be notified.</span></span> <span data-ttu-id="702cb-171">Domyślnie wszystkie zmiany wprowadzone ręcznie w profilach funkcjonalności i technicznych zostaną zachowane.</span><span class="sxs-lookup"><span data-stu-id="702cb-171">By default, all changes that have been made manually in functional and technical profiles will be stored.</span></span> <span data-ttu-id="702cb-172">Aby zastąpić te profile domyślnym zestawem parametrów z konfiguracji, kliknij przycisk **Aktualizuj** na stronach **Profile funkcjonalności łącznika** i **Profile techniczne łącznika**.</span><span class="sxs-lookup"><span data-stu-id="702cb-172">In order to override these profiles with the default set of parameters from a configuration, click **Update** on the **Connector functional profiles** page and **Connector technical profiles** page.</span></span>
 
- <span data-ttu-id="702cb-173">Utwórz **proces rejestracji fiskalnej** w oknie **Handel detaliczny > Ustawienia kanału > Integracja fiskalna > Procesy rejestracji fiskalnych** dla każdego unikatowego procesu integracji fiskalnej.</span><span class="sxs-lookup"><span data-stu-id="702cb-173">Create a **Fiscal registration process** in **Retail > Channel setup > Fiscal integration > Fiscal registration processes** for each unique process of the fiscal integration.</span></span> <span data-ttu-id="702cb-174">Proces rejestracji jest definiowany przez sekwencję etapów rejestracji oraz przez grupę łączników używaną na każdym etapie.</span><span class="sxs-lookup"><span data-stu-id="702cb-174">A registration process is defined by the sequence of the registration steps and the connector group used on each step.</span></span> 
  
  - <span data-ttu-id="702cb-175">Dodaj etapy rejestracji do procesu:</span><span class="sxs-lookup"><span data-stu-id="702cb-175">Add registration steps to the process:</span></span>
      - <span data-ttu-id="702cb-176">Kliknij przycisk **Dodaj**.</span><span class="sxs-lookup"><span data-stu-id="702cb-176">Click **Add**.</span></span>
      - <span data-ttu-id="702cb-177">Wybierz typ łącznika.</span><span class="sxs-lookup"><span data-stu-id="702cb-177">Select a connector type.</span></span>
      
      >[!NOTE]
      > <span data-ttu-id="702cb-178">To pole określa, gdzie system będzie szukał profilu technicznego łącznika — albo w profilach sprzętowych (łącznik typu **Lokalny)**, albo w profilach funkcji punktu sprzedaży (wszystkie pozostałe typy łączników fiskalnych).</span><span class="sxs-lookup"><span data-stu-id="702cb-178">This field defines where the system will search in a technical profile for the connector, either in hardware profiles for connector type **Local**, or in POS functionality profiles for other fiscal connector types.</span></span>
      
   - <span data-ttu-id="702cb-179">Wybierz grupę łączników.</span><span class="sxs-lookup"><span data-stu-id="702cb-179">Select a connector group.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="702cb-180">Kliknij przycisk **Sprawdź poprawność**, aby sprawdzić integralność struktury procesu rejestracji.</span><span class="sxs-lookup"><span data-stu-id="702cb-180">Click **Validate** to check the integrity of the registration process structure.</span></span> <span data-ttu-id="702cb-181">Zaleca się przeprowadzanie weryfikacji w następujących przypadkach:</span><span class="sxs-lookup"><span data-stu-id="702cb-181">It’s recommended that validations be made in the following cases:</span></span>
       >- <span data-ttu-id="702cb-182">W nowym procesie rejestracji po skonfigurowaniu wszystkich ustawień, w tym po utworzeniu powiązań z profilami funkcji punktu sprzedaży i profilami sprzętowymi.</span><span class="sxs-lookup"><span data-stu-id="702cb-182">For a new registration process after all the settings are completed, including binding to POS functionality profiles and hardware profiles.</span></span>
       >- <span data-ttu-id="702cb-183">Po dokonaniu zmian w istniejącym procesie rejestracji.</span><span class="sxs-lookup"><span data-stu-id="702cb-183">After making updates to an existing registration process.</span></span>

-  <span data-ttu-id="702cb-184">Powiąż procesy rejestracji fiskalnej z profilami funkcji punktu sprzedaży w oknie **Handel detaliczny > Ustawienia kanału > Ustawienia punktu sprzedaży > Profile punktu sprzedaży > Profile funkcji**.</span><span class="sxs-lookup"><span data-stu-id="702cb-184">Bind fiscal registration processes to POS functionality profiles in **Retail > Channel setup > POS setup > POS profiles > Functionality profiles**.</span></span>
   - <span data-ttu-id="702cb-185">Kliknij przycisk **Edytuj** i wybierz opcję **Identyfikator procesu** na karcie **Proces rejestracji fiskalnej**.</span><span class="sxs-lookup"><span data-stu-id="702cb-185">Click **Edit** and select a **Process number** on the **Fiscal registration process** tab.</span></span>
- <span data-ttu-id="702cb-186">Powiąż profile techniczne łączników z profilami sprzętowymi w oknie **Handel detaliczny > Ustawienia kanału > Ustawienia punktu sprzedaży > Profile punktu sprzedaży > Profile sprzętu**.</span><span class="sxs-lookup"><span data-stu-id="702cb-186">Bind the connector technical profiles to the hardware profiles in **Retail > Channel setup > POS setup > POS profiles > Hardware profiles**.</span></span>
   - <span data-ttu-id="702cb-187">Kliknij przycisk **Edytuj**, a następnie kliknij przycisk **Nowy** na karcie **Fiskalny profil techniczny**.</span><span class="sxs-lookup"><span data-stu-id="702cb-187">Click **Edit**, then click **New** on the **Fiscal technical profile** tab.</span></span>
   - <span data-ttu-id="702cb-188">Wybierz profil techniczny łącznika w polu **Identyfikator profilu**.</span><span class="sxs-lookup"><span data-stu-id="702cb-188">Select a connector technical profile in the **Profile number** field.</span></span>
   
     >[!NOTE]
     > <span data-ttu-id="702cb-189">Do profilu sprzętowego można dodać kilka profili technicznych.</span><span class="sxs-lookup"><span data-stu-id="702cb-189">You can add several technical profiles to a hardware profile.</span></span> <span data-ttu-id="702cb-190">Jednak nie jest to obsługiwane, jeśli profil sprzętowy ma więcej niż jedno przecięcie z którąkolwiek grupą łączników.</span><span class="sxs-lookup"><span data-stu-id="702cb-190">However, this is not supported if a hardware profile has more than one intersection with any connector group.</span></span> <span data-ttu-id="702cb-191">Aby uniknąć nieprawidłowych ustawień, zalecamy sprawdzenie poprawności procesu rejestracji po zaktualizowaniu wszystkich profili sprzętowych.</span><span class="sxs-lookup"><span data-stu-id="702cb-191">To avoid incorrect settings, it’s recommended that you validate the registration process after updating all the hardware profiles.</span></span>

