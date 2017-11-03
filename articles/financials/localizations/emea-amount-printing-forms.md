---
title: "Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach"
description: "Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji."
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 226eecd49fb5c4daeb701fbb019f402519999610
ms.contentlocale: pl-pl
ms.lasthandoff: 09/29/2017

---

# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a>Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach

[!include[banner](../includes/banner.md)]


Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji.

Dla firm w Estonii, na Łotwie, Litwie, w Polsce, Czechach, na Węgrzech i w Rosji można skonfigurować pełne nazwy i krótkie nazwy jednostek i podjednostek waluty. Tych nazw można używać do zmiany sposobu reprezentowania kwot w dokumentach i raportach. Na przykład kwota **100,20 PLN** może być wyświetlana jako **100 złotych 20 groszy**.

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a>Konfigurowanie długich i krótkich nazw jednostek i podjednostek walut
Aby skonfigurować długie i krótkie nazwy jednostek i podjednostek walut dla języka, wykonaj następujące kroki:

1.  Otwórz stronę **Waluty**.
2.  Służy do wybrania waluty.
3.  W okienku akcji kliknij pozycję **Odchylenie**.
4.  Aby dodać pełną nazwę i krótką nazwę dla języka, kliknij przycisk **Nowy** i wypełnij poniższe pola.
    |                                                           |                                                                                                                                                                                                                    |
    |-----------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
    | **Pole**                                                 | **Opis**                                                                                                                                                                                                    |
    | **Język**                                              | Wybierz język dla bieżącego tekstu.                                                                                                                                                                          |
    | **Mianownik l. poj. (grupa pól Nazwa jednostek)**       | Wprowadź formę liczby pojedynczej dla waluty. Na przykład forma pojedyncza złotówki to „złoty”.                                                                                                                         |
    | **Mianownik l. mn. (grupa pól Nazwa jednostek)**         | Wprowadź formę liczby mnogiej dla waluty. Na przykład wpisz „złotych”. **Uwaga:**: Pola **Dopełniacz liczby pojedynczej** i **Dopełniacz l. mn.** są dostępne zależnie od języka wybranego w polu **Język**. |
    | **Mianownik l. poj. (grupa pól Nazwa części)** | Wprowadź formę liczby pojedynczej dla podjednostki waluty.                                                                                                                                                            |
    | **Mianownik l. mn. (grupa pól Nazwa części)**         | Wprowadź formę liczby mnogiej dla podjednostki waluty.                                                                                                                                                              |
    | **Nazwa skrótowa jednostek (grupa pól Krótka nazwa)**       | Wprowadź kod ISO identyfikujący walutę. Na przykład wpisz LTL w celu identyfikowania litów.                                                                                                                             |
    | **Nazwa skrótowa części (grupa pól Krótka nazwa)**      | Wprowadź nazwę podjednostki waluty. Na przykład wpisz „groszy”.                                                                                                                                         |
    | **Spójnik „i” między jednostkami i częściami**             | Zaznacz tę opcję, aby drukować spójnik„i” między jednostkami i częściami waluty. Na przykład w fakturach i raportach kwota 100,20 PLN będzie wyświetlana jako „100 złotych i 20 groszy”.                      |

5.  Kliknij przycisk **Zapisz**.





