---
title: Tworzenie szablonu BOM
description: Szablon BOM można utworzyć przy użyciu różnych metod.
author: kamaybac
ms.date: 05/01/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMATemplateBOMTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c10bf5e758a1752e1c50c602db85e0c53ee3e662
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/29/2021
ms.locfileid: "7571504"
---
# <a name="create-a-template-bom"></a>Tworzenie szablonu BOM   

[!include [banner](../includes/banner.md)]


Szablon BOM można utworzyć przy użyciu dowolnej z niżej opisanych metod. W przypadku wszystkich metod pola **Od dnia** i **Do dnia** są opcjonalne i mają wyłącznie charakter informacyjny.

## <a name="create-a-template-bom-manually"></a>Ręczne tworzenie szablonu BOM

1.  Przejdź do **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.

2.  Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.

3.  W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Ręcznie**.

4.  W polu **Numer pozycji** wprowadź towar o typie **BOM**.

5.  W polu **Nazwa** nadaj nazwę szablonowi.

6.  Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.

7.  Kliknij przycisk **OK**.

Zostanie utworzony nowy, pusty szablon BOM.

## <a name="create-a-template-bom-based-on-another-template-bom"></a>Tworzenie szablonu BOM na podstawie innego szablonu BOM

1.  Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.

2.  Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.

3.  W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Szablon BOM**.

4.  W polu **Numer odwołania** wybierz istniejący szablon BOM, który ma zostać skopiowany do nowego szablonu BOM.

5.  W polu **Nazwa** nadaj nazwę szablonowi.

6.  Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.

7.  Kliknij przycisk **OK**.

Zostanie utworzony nowy szablon BOM przy użyciu wierszy odpowiadających wierszom pierwotnego szablonu BOM.

## <a name="create-a-template-bom-based-on-an-item-bom"></a>Tworzenie szablonu BOM na podstawie towaru BOM

1.  Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.

2.  Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.

3.  W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **BOM**.

4.  W polu **Numer odwołania** wybierz wersję BOM. Towar typu BOM zostanie skopiowany do pola **Numer pozycji**.

5.  W polu **Nazwa** nadaj nazwę szablonowi.

6.  Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.

7.  Kliknij przycisk **OK**.

Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **Listy składowe (BOM)**.

## <a name="create-a-template-bom-based-on-a-production-bom"></a>Tworzenie szablonu BOM na podstawie BOM produkcji

1.  Wybierz **Zarządzanie serwisem** \> **Ustawienia** \> **Przedmioty serwisu** \> **Szablony BOM**.

2.  Wybierz **Nowy**, co spowoduje otwarcie formularza **Utwórz szablon BOM**.

3.  W obszarze **Kopiuj wiersze BOM z odwołania** wybierz opcję **Produkcja**.

4.  W polu **Numer odwołania** wybierz BOM produkcji.

5.  W polu **Nazwa** nadaj nazwę szablonowi.

6.  Korzystając z pól **Od dnia** i **Do dnia**, określ przedział dat, w którym szablon BOM ma być aktywny.

7.  Kliknij przycisk **OK**.

Zostanie utworzony nowy szablon BOM z wierszami odpowiadającymi wierszom BOM wyświetlanym w formularzu **BOM**.

## <a name="see-also"></a>Informacje dodatkowe

[Szablony BOM ](template-boms.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]