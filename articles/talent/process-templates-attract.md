---
title: Tworzenie szablonu procesu w aplikacji Attract
description: Ten temat zawiera informacje o sposobie tworzenia szablonu procesu w aplikacji Attract.
author: andreabichsel
manager: AnnBe
ms.date: 10/15/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Talent
ms.custom: 7521
ms.assetid: 3b953d5f-6325-4c9e-8b9b-6ab0458a73f8
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2018-10-01
ms.dyn365.ops.version: AX 8.1
ms.openlocfilehash: 694835d20e3401aaeb22aa19082a2cd0e3a0163a
ms.sourcegitcommit: 434dd21450bddcd891aba0555b9853d9ba0afb6f
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/23/2019
ms.locfileid: "2010713"
---
# <a name="create-a-process-template"></a>Tworzenie szablonu procesu

[!include [banner](includes/banner.md)]

*Szablon procesu rekrutacji* zawiera wszystkie działania, które należy wykonać w procesie rekrutacji na funkcję. W tym temacie opisano elementy szablonu procesu w Microsoft Dynamics 365 Talent: Attract. Ponadto wyjaśniono, jak utworzyć szablon.

> [!NOTE]
> Tworzenie szablonu to funkcjonalność dostępna w dodatku kompleksowej obsługi rekrutacji dla aplikacji Attract.

## <a name="template-management"></a>Zarządzanie szablonami

Organizacje mogą zdecydować, czy wszyscy członkowie zespołu czy tylko administratorzy mogą tworzyć szablony procesów w aplikacji Attract. Aby skonfigurować funkcjonalność zarządzania szablonami, wybierz kolejno opcje **Centrum administracyjne** \> **Zarządzanie szablonami**. Aby umożliwić członkom zespołu tworzenie własnych szablonów, włącz funkcję zarządzania szablonami. Jeśli nie włączysz funkcjonalności zarządzania szablonami, to tylko administratorzy będą mogli tworzyć szablony.

## <a name="default-template"></a>Szablon domyślny

Tylko administratorzy mogą ustawić szablon domyślny. Szablon domyślny jest używany, jeśli nie wybrano szablonu podczas tworzenia funkcji. Aby skonfigurować szablon domyślny, wybierz kolejno opcje **Centrum administracyjne** \> **Zarządzanie szablonami**. Na karcie szablonu, który ma być szablonem domyślnym, naciśnij przycisk wielokropka (**...**), a następnie wybierz opcję **Ustaw jako domyślny**.

## <a name="create-a-process-template"></a>Tworzenie szablonu procesu

Administratorzy, osoby rekrutujące i menedżerowie zatrudniający mogą tworzyć szablony procesów. Szablon procesu składa się z *etapów* i *działań*. Etapy grupują jedno lub więcej działań. Domyślnie każdy szablon procesu ma działania Prospekt, Zgłoszenie i Oferta. Można zmieniać nazwy etapów zawierających te działania. Można dodać więcej etapów, klikając przycisk **+ Nowy etap**. W celu dodania działań do etapu można je przeciągnąć do odpowiedniego etapu albo kliknąć dwukrotnie na liście działań.

> [!NOTE]
> Nazwy etapów są widoczne dla kandydatów na stronie **Stan zgłoszenia**. Weź to pod uwagę, wybierając nazwy dla etapów.

Aby uzyskać więcej informacji o działaniach, zobacz [Działania w ramach procesu zatrudniania w aplikacji Attract](./activities-attract.md).

Aby utworzyć szablon procesu rekrutacji, wykonaj poniższe czynności.

1. Przejdź do okna **Szablony**.
2. Wybierz pozycję **Nowy**.
3. W polu **Nazwa szablonu** nadaj szablonowi nazwę, a następnie kliknij przycisk **Utwórz**.
4. Na liście **Wybierz proces zatwierdzania** wybierz pozycję **Domyślnie**, aby wprowadzić wymóg zatwierdzenia kandydatury na funkcję.
5. Włącz lub wyłącz pozwolenie na istnienie prospektów.
6. Opcjonalnie: dodaj lub usuń etapy.

    - Aby dodać etap, wybierz opcję **+ Nowy etap**.
    - Aby usunąć etap, umieść nad nim wskaźnik myszy, a następnie kliknij wyświetloną ikonę kosza.

        > [!NOTE]
        > Nie można usunąć etapów Prospekt, Zgłoszenie ani Oferta, ale można zmienić ich nazwy.

7. Opcjonalnie: dodaj lub usuń działania.

    - Aby dodać działanie, przeciągnij je z listy po prawej stronie do odpowiedniego etapu. Alternatywnie kliknij dwukrotnie działanie, a następnie wybierz etap, do którego chcesz je dodać.
    - Aby usunąć działanie, rozwiń je, a następnie kliknij przycisk kosza w nagłówku działania.

8. Wybierz opcję **Zapisz**.
