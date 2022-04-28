---
title: Konfigurowanie zaawansowanego importowania uzgodnienia konta bankowego za pomocą raportowania elektronicznego
description: W tym temacie omówiono sposób korzystania z raportowania elektronicznego w celu skonfigurowania zaawansowanego procesu importu uzgodnień bankowych dla wyciągów BAI2.
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
ms.openlocfilehash: 39f1d8ba561ab0e36346f1dfb4f70df318c92a37
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544506"
---
# <a name="set-up-advanced-bank-reconciliation-import-by-using-electronic-reporting"></a>Konfigurowanie zaawansowanego importowania uzgodnienia konta bankowego za pomocą raportowania elektronicznego

[!include [banner](../includes/banner.md)]

Funkcja Zaawansowane uzgadnianie konta bankowego umożliwia importowanie elektronicznych wyciągów bankowych, a następnie ich automatyczne uzgadnianie z transakcjami bankowymi w programie Microsoft Dynamics 365 Finance. W tym temacie wyjaśniono, jak skonfigurować funkcję importu wyciągów bankowych BAI2.

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
