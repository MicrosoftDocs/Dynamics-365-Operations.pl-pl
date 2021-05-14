---
title: Konfigurowanie opartej na atrybutach wyceny konfigurowalnych produktów
description: W tym temacie pokazano sposób konfigurowania wyceny opartej na atrybutach.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921248"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Konfigurowanie opartej na atrybutach wyceny konfigurowalnych produktów

[!include [banner](../../includes/banner.md)]

W tym temacie pokazano sposób konfigurowania wyceny opartej na atrybutach. Warunkiem wstępnym jest istnienie modelu konfiguracji produktu, który ma jeden lub więcej składników i atrybutów. W przykładzie użyto modelu produktu Głośnik o wysokiej jakości zawartego w danych firmy demonstracyjnej USMF. Zazwyczaj procedurę wykonuje menedżer produktu.


## <a name="create-a-new-price-model"></a>Tworzenie nowego modelu ceny

1. Przejdź do **Zarządzanie informacjami o produktach \> Produkty \> Modele konfiguracji produktów**.
1. Na liście zaznacz wiersz **Głośnik o wysokiej jakości**, ale nie wybieraj łącza z nazwą.
1. W okienku akcji kliknij pozycję **Model**.
1. Wybierz **Modele ceny**.
1. Wybierz pozycję **Nowy**.
1. W polu **Nazwa modelu ceny** wpisz wartość. Użyj nazwy, która sprawi, że model będzie łatwy do zidentyfikowania.  
1. W polu **Opis** wpisz wartość.
1. Wybierz opcję **Zapisz**.

## <a name="add-price-elements"></a>Dodawanie elementów ceny

1. Wybierz opcję **Edycja**. Każdy składnik w modelu produktu może mieć element ceny podstawowej i dowolną liczbę reguł wyrażenia ceny. Można również dodawać ceny w różnych walutach.  
2. W polu **Wyrażenie podstawy ceny** wpisz wartość. Na przykład wpisz 100. Wyrażenie ceny podstawowej może być wartością liczbową lub mieć formę obliczenia arytmetycznego, w którym występuje jeden lub więcej atrybutów.  
3. Wybierz opcję **Dodaj**.
4. W polu **Nazwa** wpisz `Rosewood`. Nazwa wyrażenia ceny pomaga stwierdzić, co reprezentuje element ceny. W tym przykładzie tworzymy element ceny dla opcji wykończenie głośnika palisandrem.  
5. Wybierz **Edytuj warunek**. Warunek cenowy pomaga zagwarantować, że element wyrażenia ceny jest uwzględniany w cenie sprzedaży tylko wtedy, gdy występuje określona kombinacja atrybutów.  
6. W polu **ConstraintBody** wpisz `CabinetFinish=="Rosewood"`.
7. Kliknij przycisk **OK**.
8. W polu **Wyrażenie** wpisz wartość. Na przykład wpisz `50`. 
9. Zamknij stronę.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]