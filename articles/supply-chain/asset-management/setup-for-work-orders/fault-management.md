---
title: Zarządzanie usterkami
description: W tym artykule wyjaśniono analizę zarządzania usterkami składników majątku w module Zarządzanie składnikami majątku.
author: johanhoffmann
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetFaultArea, EntAssetFaultDesigner, EntAssetFaultCopyFromObjectType, EntAssetFaultRemedy, EntAssetObjectFaultRelationRequestInfoPart, EntAssetObjectFaultRelationWorkOrderInfoPart, EntAssetFaultCreateCombinations, EntAssetObjectFaultSymptom, EntAssetObjectFaultSymptomListPage, EntAssetFaultType, EntAssetFaultSymptom, EntAssetFaultCause
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 10a4a209b54aa31c4a2f6970f46ab8b1a2cbef97
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874167"
---
# <a name="fault-management"></a>Zarządzanie usterkami

[!include [banner](../../includes/banner.md)]

 

W module Zarządzanie składnikami majątku można skorzystać z projektanta usterek, aby skonfigurować objawy usterek, obszary usterek i typy usterek w typach składników majątku. W ten sposób można zarządzać usterkami wykrytymi w składnikach majątku. Ponadto w zleceniu pracy można rejestrować przyczyny usterek i sugestie dotyczące rozwiązania usterek.

Proces rejestracji i zarządzania usterką składa się z tych kroków.

1. Utwórz listę objawów usterek, obszarów usterek i typów usterek, które mogą występować w typach składników majątku.
2. W projektancie usterek ustaw objawy, obszary usterek i typy usterek.

Poniżej przedstawiono kilka przykładów ułatwiających zrozumienie różnicy między symptomami usterek, obszarami usterek i typami usterek.

**Objawy usterki:**

- Niezbilansowane napięcia
- Krótki obwód
- Hałas
- Wyciek
- Wibracje

**Obszary usterki:**

- Elektryczny
- Maszynowy
- Hydrauliczny
- Pneumatyczny

**Typy usterek:**

- Błędne uzwojenie głównego wyciągu
- Wadliwa dioda
- Brudne uzwojenia
- Wadliwy generator
- Uszkodzony czujnik

## <a name="create-fault-symptoms"></a>Utwórz objawy usterki

Aby utworzyć listę objawów, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Objawy usterki**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W polu **Objawy usterki** wprowadź nazwę objawu usterki.
4. W polu **Opis wprowadź** opis.
5. Wybierz opcję **Zapisz**.

## <a name="create-fault-areas"></a>Tworzenie obszarów usterek

Aby utworzyć listę obszarów lub lokalizacji, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Obszary usterki**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W polu **Obszar usterki** wprowadź nazwę obszaru usterki.
4. W polu **Opis wprowadź** opis.
5. Wybierz opcję **Zapisz**.

## <a name="create-fault-types"></a>Utwórz typy usterek

Aby utworzyć listę typów usterek, które mogą być używane w projektancie usterek, należy wykonać następujące czynności.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Typy usterek**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W polu **Typ usterki** wprowadź nazwę typu usterki.
4. W polu **Opis wprowadź** opis.
5. Wybierz opcję **Zapisz**.

## <a name="set-up-the-fault-designer"></a>Konfigurowanie projektanta usterek

W projektancie usterek można skonfigurować dane usterek dla typów składników majątku.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Projektant usterek**.
2. W lewym okienku wybierz typ składnika majątku, dla którego chcesz skonfigurować rekord usterki.
3. Na skróconej karcie **Objawy usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Objaw usterki** wybierz objaw usterki.
4. Na skróconej karcie **Obszar usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Obszar usterki** wybierz obszar usterki.
5. Na skróconej karcie **Typ usterki** wybierz opcję **Dodaj wiersz**, a następnie w polu **Typ usterki** wybierz typ usterki.
6. Aby szybko utworzyć kombinacje wszystkich objawów usterek, obszarów i typów dla wybranego typu składnika, wybierz opcję **Utwórz kombinacje usterek**. Ta funkcja jest przydatna w przypadku dodawania wielu objawów usterek, obszarów i typów. Można łatwiej usunąć wiersze dla dowolnej kombinacji, która nie jest odpowiednia dla typu składnika majątku niż w celu ręcznego utworzenia nowych wierszy.

    > [!NOTE]
    > Aby skopiować ustawienia objawów usterek, obszarów i typów z jednego typu składnika majątku do wybranego typu składnika, należy wybrać opcję **Kopiuj z typu składnika majątku**.

7. Wybierz **Zapisz**, żeby zapisać zmiany.

![Strona Projektant usterek.](media/21-setup-for-work-orders.png)

## <a name="create-fault-causes"></a>Utwórz przyczyny usterek

Wykonaj poniższe kroki, aby utworzyć listę znanych przyczyn usterek, które można dodać do zlecenia pracy lub do zgłoszenia serwisowego.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Przyczyny usterek**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W polu **Przyczyny usterek** wprowadź nazwę przyczyny usterki.
4. W polu **Opis wprowadź** opis.
5. Wybierz opcję **Zapisz**.

## <a name="create-fault-remedies"></a>Stwórz środki zaradcze dla usterki

Wykonaj poniższe kroki, aby utworzyć listę znanych środków zaradczych dla usterek, które można dodać do zlecenia pracy lub do zgłoszenia serwisowego.

1. Wybierz **Zarządzanie składnikami majątku** \> **Ustawienia** \> **Usterka** \> **Środki zaradcze dla usterek**.
2. Wybierz **Nowy**, aby utworzyć rekord.
3. W polu **Środki zaradcze dla usterek** wprowadź nazwę środka zaradczego usterki.
4. W polu **Opis wprowadź** opis.
5. Wybierz opcję **Zapisz**.

> [!NOTE]
> Istnieje możliwość zmiany nazw objawów usterek, obszarów, typów, przyczyn i środków zaradczych stosownie do potrzeb. Zmiany nazwy są automatycznie odzwierciedlane w powiązanych z nią rejestracjach błędów.


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]