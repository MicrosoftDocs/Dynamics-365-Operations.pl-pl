---
title: Rozwiązywanie problemów związanych z aktualizacjami aplikacji Finance and Operations
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanycz uaktualnianiem aplikacji Finance and Operations.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2020-03-16
ms.openlocfilehash: c76b35ed3af766f42484a118a4a0407d969b5240
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/05/2020
ms.locfileid: "4683606"
---
# <a name="troubleshoot-issues-related-to-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="029d9-103">Rozwiązywanie problemów związanych z aktualizacjami aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="029d9-103">Troubleshoot issues related to upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="029d9-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="029d9-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="029d9-105">A dokładniej, ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanycz uaktualnianiem aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="029d9-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="029d9-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="029d9-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="029d9-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="029d9-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="029d9-108">Błędy synchronizacji bazy danych</span><span class="sxs-lookup"><span data-stu-id="029d9-108">Database synchronization errors</span></span>

<span data-ttu-id="029d9-109">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="029d9-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="029d9-110">Podczas próby użycia jednostki **DualWriteProjectConfiguration** w celu zaktualizowania aplikacji Finance and Operations w ramach aktualizacji platformy 30 może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu.</span><span class="sxs-lookup"><span data-stu-id="029d9-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** entity to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="029d9-111">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="029d9-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="029d9-112">Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="029d9-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="029d9-113">Otwórz Visual Studio jako administrator, a następnie otwórz drzewo obiektów aplikacji (AOT).</span><span class="sxs-lookup"><span data-stu-id="029d9-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="029d9-114">Wyszukaj **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="029d9-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="029d9-115">W drzewie obiektów aplikacji kliknij prawym przyciskiem myszy **DualWriteProjectConfiguration**, a następnie wybierz polecenie **Dodaj do nowego projektu**.</span><span class="sxs-lookup"><span data-stu-id="029d9-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="029d9-116">Wybierz **OK**, aby utworzyć nowy projekt, w którym są używane opcje domyślne.</span><span class="sxs-lookup"><span data-stu-id="029d9-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="029d9-117">W Eksploratorze rozwiązań kliknij prawym przyciskiem myszy opcję **Właściwości projektu** i określ **Synchronizację bazy danych w przypadku kompilacji** na wartość **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="029d9-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="029d9-118">Skompiluj projekt i upewnij się, że kompilacja zakończyła się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="029d9-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="029d9-119">W menu **Dynamics 365** wybierz polecenie **Synchronizuj bazę danych**.</span><span class="sxs-lookup"><span data-stu-id="029d9-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="029d9-120">Wybierz opcję **Synchronizuj**, aby przeprowadzić pełną synchronizację bazy danych.</span><span class="sxs-lookup"><span data-stu-id="029d9-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="029d9-121">Po pomyślnym zakończeniu pełnej synchronizacji bazy danych należy ponownie uruchomić krok synchronizacji bazy danych w Microsoft Dynamics Lifecycle Services (usługi LCS) i w razie potrzeby zastosować skrypty uaktualniania ręcznego, aby umożliwić kontynuowanie aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="029d9-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-entity-fields-issue-on-maps"></a><span data-ttu-id="029d9-122">Problem braku pól jednostki dla map</span><span class="sxs-lookup"><span data-stu-id="029d9-122">Missing entity fields issue on maps</span></span>

<span data-ttu-id="029d9-123">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="029d9-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="029d9-124">Na stronie **Podwójny zapis** może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu:</span><span class="sxs-lookup"><span data-stu-id="029d9-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="029d9-125">*Brak pola źródłowego nazwa pola \<field name\> w schemacie.*</span><span class="sxs-lookup"><span data-stu-id="029d9-125">*Missing source field \<field name\> in the schema.*</span></span>

![Przykład komunikatu o błędzie braku pola źródłowego](media/error_missing_field.png)

<span data-ttu-id="029d9-127">Aby rozwiązać ten problem, najpierw postępuj zgodnie z tymi krokami, aby upewnić się, że pola znajdują się w jednostce.</span><span class="sxs-lookup"><span data-stu-id="029d9-127">To fix the issue, first follow these steps to make sure that the fields are in the entity.</span></span>

1. <span data-ttu-id="029d9-128">Zaloguj się do maszyny wirtualnej aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="029d9-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="029d9-129">Przejdź do **Obszary robocze \> Zarządzanie danymi**, wybierz kafelek **Parametry struktury**, a następnie na karcie **Ustawienia tabeli** wybierz opcję **Odśwież listę jednostek**, aby odświeżyć tabele.</span><span class="sxs-lookup"><span data-stu-id="029d9-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Table settings** tab, select **Refresh entity list** to refresh the tables.</span></span>
3. <span data-ttu-id="029d9-130">Przejdź do **Obszary robocze \> Zarządzanie danymi**,wybierz kartę **Tabele danych** i upewnij się, że jednostka jest uwzględniona na liście.</span><span class="sxs-lookup"><span data-stu-id="029d9-130">Go to **Workspaces \> Data management**, select the **Data tables** tab, and make sure that the entity is listed.</span></span> <span data-ttu-id="029d9-131">Jeśli jednostka nie jest wymieniona na liście, zaloguj się do maszyny wirtualnej aplikacji Finance and Operations i upewnij się, że jednostka jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="029d9-131">If the entity isn't listed, sign in to the VM for the Finance and Operations app, and make sure the entity is available.</span></span>
4. <span data-ttu-id="029d9-132">Otwórz stronę **Mapowania tabeli** ze strony **Podwójny zapis** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="029d9-132">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="029d9-133">Wybierz opcję **Odśwież listę jednostek**, aby automatycznie wypełnić pola w mapowaniach tabeli.</span><span class="sxs-lookup"><span data-stu-id="029d9-133">Select **Refresh entity list** to automatically fill the fields in the table mappings.</span></span>

<span data-ttu-id="029d9-134">Jeśli ten błąd nadal nie jest naprawiony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="029d9-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="029d9-135">Te kroki prowadzą użytkownika przez proces usuwania jednostki, a następnie dodawania jej ponownie.</span><span class="sxs-lookup"><span data-stu-id="029d9-135">These steps guide you through the process of deleting an entity and then adding it again.</span></span> <span data-ttu-id="029d9-136">Aby uniknąć problemów, należy wykonać dokładnie te kroki.</span><span class="sxs-lookup"><span data-stu-id="029d9-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="029d9-137">W aplikacji Finance and Operations przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Tabele danych**.</span><span class="sxs-lookup"><span data-stu-id="029d9-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data tables** tile.</span></span>
2. <span data-ttu-id="029d9-138">Znajdź jednostkę, w której brakuje atrybutu.</span><span class="sxs-lookup"><span data-stu-id="029d9-138">Find the entity that is missing the attribute.</span></span> <span data-ttu-id="029d9-139">Kliknij przycisk **Modyfikuj mapowanie** obiektów docelowych na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="029d9-139">Click **Modify target mapping** in the toolbar.</span></span>
3. <span data-ttu-id="029d9-140">W okienku **Mapuj dane tymczasowe do celu** kliknij opcję **Generuj mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="029d9-140">On the **Map staging to target** pane, click **Generate mapping**.</span></span>
4. <span data-ttu-id="029d9-141">Otwórz stronę **Mapowania tabeli** ze strony **Podwójny zapis** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="029d9-141">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="029d9-142">Jeśli atrybut nie został automatycznie wypełniony na mapie, dodaj go ręcznie, klikając przycisk **Dodaj atrybut**, a następnie klikając przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="029d9-142">If the attribute is not auto-populated on the map, add it manually by clicking **Add attribute** button and then clicking **Save**.</span></span> 
6. <span data-ttu-id="029d9-143">Wybierz mapę i kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="029d9-143">Select the map and click **Run**.</span></span>
