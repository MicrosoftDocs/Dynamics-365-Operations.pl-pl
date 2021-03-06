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
# <a name="troubleshoot-issues-from-upgrades-of-finance-and-operations-apps"></a>Rozwiązywanie problemów wynikających z aktualizacji aplikacji Finance and Operations

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]



Ten temat zawiera informacje dotyczące rozwiązywania problemów dotyczących integracji o podwójnym zapisie między aplikacjami Finance and Operations i Dataverse. A dokładniej, ten temat zawiera informacje dotyczące rozwiązywania problemów, które mogą pomóc w rozwiązaniu problemów związanycz uaktualnianiem aplikacji Finance and Operations.

> [!IMPORTANT]
> Niektóre problemy, których ten problem może wymagać od roli administratora systemu lub poświadczeń administratora dzierżawcy Microsoft Azure Active Directory (Azure AD). W sekcji dotyczącej każdego zagadnienia wyjaśniono, czy określona rola lub poświadczenia są wymagane.

## <a name="database-synchronization-errors"></a>Błędy synchronizacji bazy danych

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Podczas próby użycia tabeli **DualWriteProjectConfiguration** w celu zaktualizowania aplikacji Finance and Operations w ramach aktualizacji platformy 30 może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu.

```console
Infolog diagnostic message: 'Cannot select a row in Dual write project sync (DualWriteProjectConfiguration). The SQL database has issued an error.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Object Server Database Synchronizer: ' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: '[Microsoft][ODBC Driver 17 for SQL Server][SQL Server]Invalid column name 'ISDELETE'.' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'SELECT T1.PROJECTNAME,T1.EXTERNALENTITYNAME,T1.INTERNALENTITYNAME,T1.EXTERNALENVIRONMENTURL,T1.STATUS,T1.ENABLEBATCHLOOKUP,T1.PARTITIONMAP,T1.QUERYFILTEREXPRESSION,T1.INTEGRATIONKEY,T1.ISDELETE,T1.ISDEBUGMODE,T1.RECVERSION,T1.PARTITION,T1.RECID FROM DUALWRITEPROJECTCONFIGURATION T1 WHERE (PARTITION=5637144576)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'session 1043 (Admin)' on category 'Error'. 10/28/2019 15:18:20: Infolog diagnostic message: 'Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN.' on category 'Error'.
10/28/2019 15:18:20: Application configuration sync failed.
Microsoft.Dynamics.AX.Framework.Database.TableSyncException: Custom action threw exception(s), please investigate before synchronizing again: 'InfoException:Stack trace: Call to TTSCOMMIT without first calling TTSBEGIN."
```

Aby naprawić problem, należy wykonać następujące czynności.

1. Zaloguj się do maszyny wirtualnej (VM) aplikacji Finance and Operations.
2. Otwórz Visual Studio jako administrator, a następnie otwórz drzewo obiektów aplikacji (AOT).
3. Wyszukaj **DualWriteProjectConfiguration**.
4. W drzewie obiektów aplikacji kliknij prawym przyciskiem myszy **DualWriteProjectConfiguration**, a następnie wybierz polecenie **Dodaj do nowego projektu**. Wybierz **OK**, aby utworzyć nowy projekt, w którym są używane opcje domyślne.
5. W Eksploratorze rozwiązań kliknij prawym przyciskiem myszy opcję **Właściwości projektu** i określ **Synchronizację bazy danych w przypadku kompilacji** na wartość **Prawda**.
6. Skompiluj projekt i upewnij się, że kompilacja zakończyła się pomyślnie.
7. W menu **Dynamics 365** wybierz polecenie **Synchronizuj bazę danych**.
8. Wybierz opcję **Synchronizuj**, aby przeprowadzić pełną synchronizację bazy danych.
9. Po pomyślnym zakończeniu pełnej synchronizacji bazy danych należy ponownie uruchomić krok synchronizacji bazy danych w Microsoft Dynamics Lifecycle Services (usługi LCS) i w razie potrzeby zastosować skrypty uaktualniania ręcznego, aby umożliwić kontynuowanie aktualizacji.

## <a name="missing-table-columns-issue-on-maps"></a>Problem z brakującymi kolumnami tabeli na mapach

**Wymagana rola w celu rozwiązania problemu:** administrator systemu

Na stronie **Podwójny zapis** może zostać wyświetlony komunikat o błędzie podobny do następującego przykładu:

*Brak pola źródłowego nazwa pola \<field name\> w schemacie.*

![Przykład komunikatu o błędzie braku kolumny źródłowej](media/error_missing_field.png)

Aby rozwiązać ten problem, najpierw postępuj zgodnie z tymi krokami, aby upewnić się, że kolumny znajdują się w tabeli.

1. Zaloguj się do maszyny wirtualnej aplikacji Finance and Operations.
2. Przejdź do **Obszary robocze \> Zarządzanie danymi**, wybierz kafelek **Parametry struktury**, a następnie na karcie **Ustawienia tabeli** wybierz opcję **Odśwież listę tabel**, aby odświeżyć tabele.
3. Przejdź do **Obszary robocze \> Zarządzanie danymi**,wybierz kartę **Tabele danych** i upewnij się, że tabela jest uwzględniona na liście. Jeśli tabela nie jest wymieniona na liście, zaloguj się do maszyny wirtualnej aplikacji Finance and Operations i upewnij się, że tabela jest dostępna.
4. Otwórz stronę **Mapowania tabeli** ze strony **Podwójny zapis** w aplikacji Finance and Operations.
5. Wybierz opcję **Odśwież listę tabel**, aby automatycznie wypełnić kolumny w mapowaniach tabeli.

Jeśli ten błąd nadal nie jest naprawiony, wykonaj następujące kroki.

> [!IMPORTANT]
> Te kroki prowadzą użytkownika przez proces usuwania tabeli, a następnie dodawania jej ponownie. Aby uniknąć problemów, należy wykonać dokładnie te kroki.

1. W aplikacji Finance and Operations przejdź do **Obszary robocze \> Zarządzanie danymi** i wybierz kafelek **Tabele danych**.
2. Znajdź tabelę, w której brakuje atrybutu. Kliknij przycisk **Modyfikuj mapowanie** obiektów docelowych na pasku narzędzi.
3. W okienku **Mapuj dane tymczasowe do celu** kliknij opcję **Generuj mapowanie**.
4. Otwórz stronę **Mapowania tabeli** ze strony **Podwójny zapis** w aplikacji Finance and Operations.
5. Jeśli atrybut nie został automatycznie wypełniony na mapie, dodaj go ręcznie, klikając przycisk **Dodaj atrybut**, a następnie klikając przycisk **Zapisz**. 
6. Wybierz mapę i kliknij przycisk **Uruchom**.


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]