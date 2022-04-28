---
title: Konfigurowanie i generowanie plików płatności dodatnich za pomocą raportowania elektronicznego
description: W tym temacie wyjaśniono, jak skonfigurować płacę dodatnią za pomocą raportowania elektronicznego.
author: panolte
ms.date: 03/20/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BankPositivePayFormat
audience: Application User
ms.reviewer: twheeloc
ms.custom: 88433
ms.assetid: 73f3dcf6-040a-44ad-9512-7b3e0d17a571
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
ms.openlocfilehash: 43dd1a9cba1fe8df5cff26fe76af7e2957a0d6a4
ms.sourcegitcommit: cf7d4af11bf85638ee831a28ea5ee1a1e041a675
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/04/2022
ms.locfileid: "8544490"
---
# <a name="set-up-positive-pay-files-by-using-electronic-reporting"></a>Konfigurowanie plików płatności dodatnich za pomocą raportowania elektronicznego

Konfigurowanie płatności dodatnich w celu generowania elektronicznej listy czeków dostarczanych do banku. Gdy czek zostanie przekazany do banku, bank porównuje go z listą czeków. Jeśli czek pasuje do czeku na liście, wówczas bank rozlicza czek. Jeśli czek nie pasuje do czeku na liście, bank wstrzymuje czek w celu sprawdzenia.

## <a name="set-up-the-electronic-reporting-configuration"></a>Skonfiguruj konfigurację raportowania elektronicznego

1. Otwórz **Miejsca pracy \> Electroniczne Raportowanie**.
2. Na kafelku dla dostawcy konfiguracji **Microsoft** wybierz **Repozytoria**.
3. Wybierz opcję **Globalny**, a następnie wybierz opcję **Otwórz**.
4. Jeśli konieczne jest nawiązanie połączenia z repozytorium, wybierz niebieskie łącze w oknie dialogowym.
5. Na liście konfiguracji znajdź i wybierz **Pozytywny model wynagradzania \> Dodatni format wynagrodzenia**.
6. Na karcie **Wersje** FastTab wybierz najnowszą wersję, a następnie wybierz **Import**.

## <a name="set-up-a-positive-pay-format"></a>Konfigurowanie formatu płatności dodatnich

1. Wybierz kolejno opcje **Zarządzanie gotówką i bankami \> Ustawienia \> Dodatni format wynagrodzenia**.
2. Wybierz pozycję **Nowy**.
3. Ustaw pola **Format płatności** i **Opis**.
4. Zaznacz pole **Ogólny elektroniczny format eksportu**.
5. Ustaw w polu **konfiguracji format eksportu** format płatności **dodatnich**.

## <a name="assign-a-positive-pay-format-to-a-bank-account"></a>Przypisywanie formatu płatności dodatnich do konta bankowego

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Otwórz konto bankowe.
3. Na skróconej **karcie** Ogólne ustaw **format płatności dodatnich** na format utworzony wcześniej.
4. Ustaw w polu **Data rozpoczęcia płatności dodatnich** bieżącą datę.

## <a name="generate-a-positive-pay-file"></a>Generuj plik płatności dodatnich

1. Kliknij kolejno opcje **Zarządzanie gotówką i bankami \> Konta bankowe \> Konta bankowe**.
2. Otwórz konto bankowe, dla których ustawiono płatności dodatnie.
3. Wybierz opcję **Zarządzaj płatnościami \> Dodatnie wynagrodzenie \> Dodatnia kartoteka wynagrodzeń**.
4. Ustaw pole **Data graniczna**. Zostaną uwzględnione czeki wygenerowane wcześniej niż ta data.

Wynikowy plik XML zostanie pobrany.
