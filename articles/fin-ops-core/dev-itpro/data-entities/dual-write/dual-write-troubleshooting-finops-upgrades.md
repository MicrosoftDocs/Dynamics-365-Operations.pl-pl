---
title: Rozwiązywanie problemów wynikających z aktualizacji aplikacji Finance and Operations
description: Ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanycz uaktualnianiem aplikacji Finance and Operations.
author: RamaKrishnamoorthy
ms.date: 03/16/2020
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 97509ac662fad6181cbd60e5e0a44f674410acb9
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 03/31/2021
ms.locfileid: "5754045"
---
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a><span data-ttu-id="f1720-103">Rozwiązywanie problemów wynikających z aktualizacji aplikacji Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="f1720-103">Troubleshoot issues from upgrades of Finance and Operations apps</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



<span data-ttu-id="f1720-104">Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="f1720-104">This topic provides troubleshooting information for dual-write integration between Finance and Operations apps and Dataverse.</span></span> <span data-ttu-id="f1720-105">A dokładniej, ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanycz uaktualnianiem aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1720-105">Specifically, it provides information that can help you fix issues that are related to upgrades of Finance and Operations apps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1720-106">Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="f1720-106">Some of the issues that this topic addresses might require either the system admin role or Microsoft Azure Active Directory (Azure AD) tenant admin credentials.</span></span> <span data-ttu-id="f1720-107">W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.</span><span class="sxs-lookup"><span data-stu-id="f1720-107">The section for each issue explains whether a specific role or credentials are required.</span></span>

## <a name="database-synchronization-errors"></a><span data-ttu-id="f1720-108">Błędy synchronizacji bazy danych</span><span class="sxs-lookup"><span data-stu-id="f1720-108">Database synchronization errors</span></span>

<span data-ttu-id="f1720-109">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="f1720-109">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="f1720-110">Podczas próby użycia tabeli **DualWriteProjectConfiguration** w celu zaktualizowania aplikacji Finance and Operations w ramach aktualizacji platformy 30 może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu.</span><span class="sxs-lookup"><span data-stu-id="f1720-110">You might receive an error message that resembles the following example when you try to use the **DualWriteProjectConfiguration** table to update a Finance and Operations app to Platform update 30.</span></span>

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

<span data-ttu-id="f1720-111">Aby naprawić problem, należy wykonać następujące czynności.</span><span class="sxs-lookup"><span data-stu-id="f1720-111">To fix the issue, follow these steps.</span></span>

1. <span data-ttu-id="f1720-112">Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1720-112">Sign in to the virtual machine (VM) for the Finance and Operations app.</span></span>
2. <span data-ttu-id="f1720-113">Otwórz Visual Studio jako administrator, a następnie otwórz drzewo obiektów aplikacji (AOT).</span><span class="sxs-lookup"><span data-stu-id="f1720-113">Open Visual Studio as an admin, and open the Application Object Tree (AOT).</span></span>
3. <span data-ttu-id="f1720-114">Wyszukaj **DualWriteProjectConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="f1720-114">Search for **DualWriteProjectConfiguration**.</span></span>
4. <span data-ttu-id="f1720-115">W drzewie obiektów aplikacji kliknij prawym przyciskiem myszy **DualWriteProjectConfiguration**, a następnie wybierz polecenie **Dodaj do nowego projektu**.</span><span class="sxs-lookup"><span data-stu-id="f1720-115">In the AOT, right-click **DualWriteProjectConfiguration**, and select **Add to new project**.</span></span> <span data-ttu-id="f1720-116">Wybierz **OK**, aby utworzyć nowy projekt, w którym są używane opcje domyślne.</span><span class="sxs-lookup"><span data-stu-id="f1720-116">Select **OK** to create the new project that uses default options.</span></span>
5. <span data-ttu-id="f1720-117">W Eksploratorze rozwiązań kliknij prawym przyciskiem myszy opcję **Właściwości projektu** i określ **Synchronizację bazy danych w przypadku kompilacji** na wartość **Prawda**.</span><span class="sxs-lookup"><span data-stu-id="f1720-117">In Solution Explorer, right-click **Project properties**, and set **Synchronize Database on Build** to **True**.</span></span>
6. <span data-ttu-id="f1720-118">Skompiluj projekt i upewnij się, że kompilacja zakończyła się pomyślnie.</span><span class="sxs-lookup"><span data-stu-id="f1720-118">Build the project, and confirm that the build is successful.</span></span>
7. <span data-ttu-id="f1720-119">W menu **Dynamics 365** wybierz polecenie **Synchronizuj bazę danych**.</span><span class="sxs-lookup"><span data-stu-id="f1720-119">On the **Dynamics 365** menu, select **Synchronize database**.</span></span>
8. <span data-ttu-id="f1720-120">Wybierz opcję **Synchronizuj**, aby przeprowadzić pełną synchronizację bazy danych.</span><span class="sxs-lookup"><span data-stu-id="f1720-120">Select **Synchronize** to do a full database synchronization.</span></span>
9. <span data-ttu-id="f1720-121">Po pomyślnym zakończeniu pełnej synchronizacji bazy danych należy ponownie uruchomić krok synchronizacji bazy danych w Microsoft Dynamics Lifecycle Services (usługi LCS) i w razie potrzeby zastosować skrypty uaktualniania ręcznego, aby umożliwić kontynuowanie aktualizacji.</span><span class="sxs-lookup"><span data-stu-id="f1720-121">After the full database synchronization is successful, rerun the database synchronization step in Microsoft Dynamics Lifecycle Services (LCS) and use the manual upgrade scripts as applicable, so that you can proceed with the update.</span></span>

## <a name="missing-table-columns-issue-on-maps"></a><span data-ttu-id="f1720-122">Problem z brakującymi kolumnami tabeli na mapach</span><span class="sxs-lookup"><span data-stu-id="f1720-122">Missing table columns issue on maps</span></span>

<span data-ttu-id="f1720-123">**Wymagana rola w celu rozwiązania problemu:** administrator systemu</span><span class="sxs-lookup"><span data-stu-id="f1720-123">**Required role to fix the issue:** System admin</span></span>

<span data-ttu-id="f1720-124">Na stronie **Podwójny zapis** może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu:</span><span class="sxs-lookup"><span data-stu-id="f1720-124">On the **Dual-write** page, you might receive an error message that resembles the following example:</span></span>

<span data-ttu-id="f1720-125">*Brak pola źródłowego nazwa pola \<field name\> w schemacie.*</span><span class="sxs-lookup"><span data-stu-id="f1720-125">*Missing source field \<field name\> in the schema.*</span></span>

![Przykład komunikatu o błędzie braku kolumny źródłowej](media/error_missing_field.png)

<span data-ttu-id="f1720-127">Aby rozwiązać ten problem, najpierw postępuj zgodnie z tymi krokami, aby upewnić się, że kolumny znajdują się w tabeli.</span><span class="sxs-lookup"><span data-stu-id="f1720-127">To fix the issue, first follow these steps to make sure that the columns are in the table.</span></span>

1. <span data-ttu-id="f1720-128">Zaloguj się do maszyny wirtualnej aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1720-128">Sign in to the VM for the Finance and Operations app.</span></span>
2. <span data-ttu-id="f1720-129">Przejdź do **Obszary robocze \> Zarządzanie danymi**, wybierz kafelek **Parametry struktury**, a następnie na karcie **Ustawienia tabeli** wybierz opcję **Odśwież listę tabel**, aby odświeżyć tabele.</span><span class="sxs-lookup"><span data-stu-id="f1720-129">Go to **Workspaces \> Data management**, select the **Framework parameters** tile, and then, on the **Table settings** tab, select **Refresh table list** to refresh the tables.</span></span>
3. <span data-ttu-id="f1720-130">Przejdź do **Obszary robocze \> Zarządzanie danymi**,wybierz kartę **Tabele danych** i upewnij się, że tabela jest uwzględniona na liście.</span><span class="sxs-lookup"><span data-stu-id="f1720-130">Go to **Workspaces \> Data management**, select the **Data tables** tab, and make sure that the table is listed.</span></span> <span data-ttu-id="f1720-131">Jeśli tabela nie jest wymieniona na liście, zaloguj się do maszyny wirtualnej aplikacji Finance and Operations i upewnij się, że tabela jest dostępna.</span><span class="sxs-lookup"><span data-stu-id="f1720-131">If the table isn't listed, sign in to the VM for the Finance and Operations app, and make sure the table is available.</span></span>
4. <span data-ttu-id="f1720-132">Otwórz stronę **Mapowania tabeli** ze strony **Podwójny zapis** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1720-132">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="f1720-133">Wybierz opcję **Odśwież listę tabel**, aby automatycznie wypełnić kolumny w mapowaniach tabeli.</span><span class="sxs-lookup"><span data-stu-id="f1720-133">Select **Refresh table list** to automatically fill the columns in the table mappings.</span></span>

<span data-ttu-id="f1720-134">Jeśli ten błąd nadal nie jest naprawiony, wykonaj następujące kroki.</span><span class="sxs-lookup"><span data-stu-id="f1720-134">If the issue still isn't fixed, follow these steps.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f1720-135">Te kroki prowadzą użytkownika przez proces usuwania tabeli, a następnie dodawania jej ponownie.</span><span class="sxs-lookup"><span data-stu-id="f1720-135">These steps guide you through the process of deleting a table and then adding it again.</span></span> <span data-ttu-id="f1720-136">Aby uniknąć problemów, należy wykonać dokładnie te kroki.</span><span class="sxs-lookup"><span data-stu-id="f1720-136">To avoid issues, be sure to follow the steps exactly.</span></span>

1. <span data-ttu-id="f1720-137">W aplikacji Finance and Operations przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Tabele danych**.</span><span class="sxs-lookup"><span data-stu-id="f1720-137">In the Finance and Operations app, go to **Workspaces \> Data management**, and select the **Data tables** tile.</span></span>
2. <span data-ttu-id="f1720-138">Znajdź tabelę, w której brakuje atrybutu.</span><span class="sxs-lookup"><span data-stu-id="f1720-138">Find the table that is missing the attribute.</span></span> <span data-ttu-id="f1720-139">Kliknij przycisk **Modyfikuj mapowanie** obiektów docelowych na pasku narzędzi.</span><span class="sxs-lookup"><span data-stu-id="f1720-139">Click **Modify target mapping** in the toolbar.</span></span>
3. <span data-ttu-id="f1720-140">W okienku **Mapuj dane tymczasowe do celu** kliknij opcję **Generuj mapowanie**.</span><span class="sxs-lookup"><span data-stu-id="f1720-140">On the **Map staging to target** pane, click **Generate mapping**.</span></span>
4. <span data-ttu-id="f1720-141">Otwórz stronę **Mapowania tabeli** ze strony **Podwójny zapis** w aplikacji Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="f1720-141">Open the **Table mapping** page from the **Dual-write** page in the Finance and Operations app.</span></span>
5. <span data-ttu-id="f1720-142">Jeśli atrybut nie został automatycznie wypełniony na mapie, dodaj go ręcznie, klikając przycisk **Dodaj atrybut**, a następnie klikając przycisk **Zapisz**.</span><span class="sxs-lookup"><span data-stu-id="f1720-142">If the attribute is not auto-populated on the map, add it manually by clicking **Add attribute** button and then clicking **Save**.</span></span> 
6. <span data-ttu-id="f1720-143">Wybierz mapę i kliknij przycisk **Uruchom**.</span><span class="sxs-lookup"><span data-stu-id="f1720-143">Select the map and click **Run**.</span></span>


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]