---
title: Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach
description: Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji.
author: anasyash
manager: AnnBe
ms.date: 08/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Currency
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.custom: 264254
ms.search.region: Czech Republic, Estonia, Hungary, Latvia, Lithuania, Poland, Russia
ms.author: v-elgolu
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 29d9369aaeef8cb62d4dd8f9eb8fcc171a28ca6a
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/27/2019
ms.locfileid: "2176163"
---
# <a name="update-how-amounts-are-displayed-on-reports-and-documents"></a>Aktualizowanie sposobu wyświetlania kwot w raportach i dokumentach

[!include [banner](../includes/banner.md)]

Ten temat zawiera informacje dotyczące aktualizacji sposobu wyświetlania kwot w raportach i innych dokumentach dla Estonii, Łotwy, Litwy, Polski, Czech, Węgier i Rosji.

Dla firm w Estonii, na Łotwie, Litwie, w Polsce, Czechach, na Węgrzech i w Rosji można skonfigurować pełne nazwy i krótkie nazwy jednostek i podjednostek waluty. Tych nazw można używać do zmiany sposobu reprezentowania kwot w dokumentach i raportach. Na przykład kwota **100,20 PLN** może być wyświetlana jako **100 złotych 20 groszy**.

## <a name="set-up-full-and-short-names-for-currency-units-and-subunits"></a>Konfigurowanie długich i krótkich nazw jednostek i podjednostek walut
Aby skonfigurować długie i krótkie nazwy jednostek i podjednostek walut dla języka, wykonaj następujące kroki:

1. Otwórz stronę **Waluty**.
2. Służy do wybrania waluty.
3. W Okienku akcji kliknij pozycję **Odchylenie**.
4. Aby dodać pełną nazwę i krótką nazwę dla języka, kliknij przycisk **Nowy** i wpisz informacje w poniższych polach.

   |                                                                        |                                                                                                                                                                                                                                                                        |
   |------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   |                         <strong>Pole</strong>                         |                                                                                                                      <strong>Opis</strong>                                                                                                                      |
   |                       <strong>Język</strong>                        |                                                                                                               Wybierz język dla bieżącego tekstu.                                                                                                                |
   |    <strong>Mianownik l. poj. (grupa pól Nazwa jednostek)</strong>    |                                                                                       Wprowadź formę liczby pojedynczej dla waluty. Na przykład forma pojedyncza złotówki to „złoty”.                                                                                       |
   |     <strong>Mianownik l. mn. (grupa pól Nazwa jednostek)</strong>     | Wprowadź formę liczby mnogiej dla waluty. Na przykład wpisz „złotych”. <strong>Uwaga:</strong>: Pola <strong>Dopełniacz liczby pojedynczej</strong> i <strong>Dopełniacz l. mn.</strong> są dostępne zależnie od języka wybranego w polu <strong>Język</strong>. |
   | <strong>Mianownik l. poj. (grupa pól Nazwa części)</strong> |                                                                                                        Wprowadź formę liczby pojedynczej dla podjednostki waluty.                                                                                                         |
   |     <strong>Mianownik l. mn. (grupa pól Nazwa części)</strong>     |                                                                                                         Wprowadź formę liczby mnogiej dla podjednostki waluty.                                                                                                          |
   |    <strong>Nazwa skrótowa jednostek (grupa pól Krótka nazwa)</strong>    |                                                                                         Wprowadź kod ISO identyfikujący walutę. Na przykład wpisz LTL w celu identyfikowania litów.                                                                                         |
   |   <strong>Nazwa skrótowa części (grupa pól Krótka nazwa)</strong>    |                                                                                               Wprowadź nazwę podjednostki waluty. Na przykład wpisz „groszy”.                                                                                               |
   |       <strong>Spójnik „i” między jednostkami i częściami</strong>       |                                     Zaznacz tę opcję, aby drukować spójnik„i” między jednostkami i częściami waluty. Na przykład w fakturach i raportach kwota 100,20 PLN będzie wyświetlana jako „100 złotych i 20 groszy”.                                      |
   |       <strong>Rodzaj</strong>       |  Wybierz **Mężczyzna**, **Kobieta** lub **Neutralne**. Ten parametr może mieć wpływ na tekst kwoty odchylenia, która jest wyświetlana w tekście języka lokalnego na Zamówieniu gotówkowym. Na przykład po skonfigurowaniu **Płci** dla waluty euro jako **Neutralne**, kwota 1,01 euro jest zapisywana w języku czeskim na zamówieniu gotówkowym jako *Edno euro 01 cent*.  |

5. Wybierz opcję **Zapisz**.

