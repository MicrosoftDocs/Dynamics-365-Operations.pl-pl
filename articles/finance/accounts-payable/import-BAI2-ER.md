---
title: Konfigurowanie zaawansowanego importowania uzgodnienia konta bankowego za pomocą raportowania elektronicznego
description: W tym temacie omówiono sposób korzystania z raportowania elektronicznego w celu skonfigurowania zaawansowanego procesu importu uzgodnień bankowych.
author: panolte
ms.date: 03/30/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankStatementFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 10.0.25
ms.openlocfilehash: 30530a9870ba2ff0546237d2698d1675afa78104
ms.sourcegitcommit: 2b4ee1fe05792332904396b5f495d74f2a217250
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/18/2022
ms.locfileid: "8770202"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Konfigurowanie zaawansowanego importowania uzgodnienia konta bankowego za pomocą raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Funkcja Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych, a następnie ich automatyczne uzgadnianie z transakcjami bankowymi w programie Microsoft Dynamics 365 Finance. W tym temacie wyjaśniono, jak skonfigurować funkcję importu wyciągów bankowych. Konfiguracja importu wyciągów bankowych różni się i zależy od formatu elektronicznych wyciągów bankowych. Microsoft Dynamics 365 Finance obsługuje standardowo trzy formaty wyciągów bankowych: ISO20022, MT940 i BAI2. 

## <a name="set-up-the-electronic-reporting-configuration"></a>Skonfiguruj konfigurację raportowania elektronicznego

1. Otwórz **Miejsca pracy \> Electroniczne Raportowanie**.
2. Na kafelku dla dostawcy konfiguracji **Microsoft** wybierz **Repozytoria**.
3. Wybierz opcję **Globalny**, a następnie wybierz opcję **Otwórz**.
4. Jeśli konieczne jest nawiązanie połączenia z repozytorium, wybierz niebieskie łącze w oknie dialogowym.
5. Na liście konfiguracji znajdź **Wzór wyciągu bankowego \> Model wyciągu bankowego BAI2**.
6. Wybieranie formatu **BAI2**.
7. Na karcie **Wersje** FastTab wybierz najnowszą wersję, a następnie wybierz **Import**.

## <a name="set-up-the-bank-statement-format"></a>Ustawianie formatu wyciągu bankowego

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Ustawienia zaawansowanego uzgodnienia konta bankowego \> Format wyciągu bankowego**.
2. Wybierz pozycję **Nowy**.
3. Ustaw pola **Format oświadczenia** i **Nazwa**.
4. Zaznacz pole **Ogólny elektroniczny format importu**.
5. Ustaw w polu **Konfiguracja formatu importu** format **BAI2**.

## <a name="set-up-the-bank-account"></a>Zakładanie konta bankowego

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Otwórz konto bankowe.
3. Na karcie skrócone **Uzgodnienie** w opcji **Zaawansowane uzgadnianie konta bankowego** zaznacz wartość **Tak**.
4. W polu **Format wyciągu** ustaw format, który został utworzony wcześniej **BAI2**.

## <a name="import-the-bank-statement"></a>Importuj wyciąg bankowy

1. Przejdź do opcji **Zarządzanie gotówką i bankami \> Uzgodnienie wyciągów bankowych \> Wyciągi bankowe**.
2. W górnej części strony **Wyciągi bankowe** wybierz pozycję **Import wyciągu**.
3. Ustaw pole **Konto bankowe** na konto bankowe z wyciągu.
4. W polu **Format wyciągu** ustaw format, który został utworzony wcześniej **BAI2**.
5. Wybierz **Przeglądaj** i wybierz plik **BAI**.
6. Wybierz pozycję **Przekaż**.
7. Wybierz przycisk **OK**, aby zaimportować wybrany plik.


## <a name="examples-of-bank-statement-formats-and-technical-layouts"></a>Przykłady formatów i układów technicznych i wyciągów bankowych
Poniżej przedstawiono przykłady definicji układów technicznych plików importu zaawansowanego uzgadniania konta bankowego i trzy powiązane przykładowe pliki wyciągów bankowych: [Import file examples](//download.microsoft.com/download/8/e/c/8ec8d2d0-eb8c-41fb-ad8c-f01a4d670a44/Dynamics365FinanceAdvancedBankStatementLayouts.xlsx)  

| Definicja układu technicznego                             | Przykładowy plik wyciągu bankowego          |
|---------------------------------------------------------|--------------------------------------|
| DynamicsAXMT940Layout | [MT940StatementExample](//download.microsoft.com/download/2/d/c/2dcc4e55-ddc8-4a74-b79c-250fae201c3c/mt940StatementExample.txt)     |
| DynamicsAXISO20022Layout | [ISO20022StatementExample](https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fdownload.microsoft.com%2Fdownload%2F1%2F5%2F5%2F155d84ed-c250-48f3-b0b1-c5a431e7855b%2FISO20022-MultipleStatements.xml&data=04%7C01%7CRobert.Schlomann%40microsoft.com%7C30d0c233cb6546547d0a08d8f4965edc%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637528273956712775%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C1000&sdata=3VzvLZK%2BO8PjuI7XVdC6rD2j3nUJfteo7zFp%2B1s9BwM%3D&reserved=0)             |
| DynamicsAXBAI2Layout    | [BAI2StatementExample](//download.microsoft.com/download/1/1/6/11693f57-bfc1-4993-a274-5fb978be70fa/BAI2StatementExample.txt)     |

