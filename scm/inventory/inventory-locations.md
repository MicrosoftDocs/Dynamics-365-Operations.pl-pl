---
title: Magazyny
description: "Lokalizacje w magazynach są używane w podstawowym module zarządzania magazynem (WMS I) do ustalania, gdzie towary będą przechowywane i skąd będą pobierane w magazynie zarządzanym w ramach WMS I."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: WMSLocation
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 2134
ms.assetid: 69bf6922-4151-447f-b678-4ba95637f54c
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: 2539f94d49b49c88b600b09418e90eaa11b8c3e4
ms.contentlocale: pl-pl
ms.lasthandoff: 04/25/2017


---

# <a name="inventory-locations"></a>Magazyny

[!include[banner](../includes/banner.md)]


Lokalizacje w magazynach są używane w podstawowym module zarządzania magazynem (WMS I) do ustalania, gdzie towary będą przechowywane i skąd będą pobierane w magazynie zarządzanym w ramach WMS I.

Ten temat dotyczy funkcji w module Zarządzanie zapasami. Nie ma zastosowania do funkcji w module Zarządzanie magazynem.

Termin lokalizacja dotyczy miejsca, w którym towary są przechowywane i z którego są wyjmowane.

Dla każdej lokalizacji można także określić miejsce, w którym jest wkładany towar. Domyślnie te miejsca są identyczne. Zazwyczaj towary są wkładane i wyjmowane po tej samej stronie lokalizacji, jednak ta zasada nie zawsze obowiązuje. Na przykład towary przechowywane na ruchomych regałach są wkładane z jednego korytarza, a wyjmowane z drugiego. Głównego wprowadzenia dokonuje się przez nazwę lokalizacji, która jest zwykle określana na podstawie jej współrzędnych: magazyn, korytarz, regał, półka i pojemnik. Tę nazwę lub identyfikator można wprowadzać ręcznie lub generować na podstawie współrzędnych lokalizacji — na przykład 01-02-03-4 oznacza korytarz 1, regał 2, półkę 3 i pojemnik 4 na stronie Magazyny.
Właściwości lokalizacji
-------------------

Lokalizacja ma następujące właściwości:
-   Rozmiar (wysokość, szerokość, głębokość, a przez to objętość)
-   Magazyn, korytarz, regał, półka oraz pojemnik.
-   Typ lokalizacji (lokalizacja zbiorcza, lokalizacji pobrania, dok rozładunkowy, dok załadunkowy, lokalizacja przyjęcia z produkcji, lokalizacja inspekcji lub supermarket kanban)

W systemach online w celu sprawdzenia, czy operator wybrał prawidłową lokalizację dla określonego towaru, można użyć funkcji Tekst sprawdzania. Ten tekst sprawdzania można utworzyć ręcznie lub użyć domyślnego.

## <a name="sort-codes"></a>Kody sortowania
Kody sortowania umożliwiają optymalizację obsługi wierszy pobrań, które pozwalają uzyskać szczegółowe informacje wymagane do pobierania towarów z magazynu, w tym kolejność pobierania. Kody sortowania mogą być określane na podstawie korytarza lub innych współrzędnych, można je także przypisywać ręcznie do konkretnej lokalizacji.

## <a name="blocked-locations"></a>Lokalizacje zablokowane
Sporadycznie konieczne może być wskazanie lokalizacji, która jest przez jakiś czas zablokowana, na przykład w celu dokonania napraw. Innym razem może zaistnieć potrzeba zablokowania tylko wejścia lub tylko wyjścia.
Struktura drzewa
--------------

Na stronie Magazyny można wyświetlić układ magazynu w postaci struktury drzewa na podstawie współrzędnych lokalizacji magazynu, w zdefiniowanym formacie wyświetlania.
Obsługa magazynów za pomocą formularza magazynu
---------------------------------------------------

Można skopiować lokalizacje z jednego magazynu do innego i tworzyć lokalizacje za pomocą kreatora. Przed uruchomieniem kreatora należy upewnić się, że masz zdefiniowane domyślne nazwy lokalizacji na stronie Magazyn.



<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie nowego układu magazynu (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/create-a-new-warehouse-layout/)




