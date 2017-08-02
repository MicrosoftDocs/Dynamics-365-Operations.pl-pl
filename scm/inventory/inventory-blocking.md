---
title: "Blokowanie zapasów"
description: "Ten artykuł zawiera omówienie mechanizmu blokowania zapasów, który jest częścią procesu kontroli jakości w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Używając blokowania, można zapobiec przetwarzaniu i zużywaniu zapasów."
author: YuyuScheller
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: InventBlocking, InventQualityOrderTable
audience: Application User
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 2094
ms.assetid: 1968e32f-eff9-4c17-8f7f-a870f0c38fbc
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 9262dcaa3b326d8c31b7d7416b102920795da94b
ms.openlocfilehash: 4c5ebea58630188615fb4c22cc9da5215461e513
ms.contentlocale: pl-pl
ms.lasthandoff: 06/13/2017


---

# <a name="inventory-blocking"></a>Blokowanie zapasów

[!include[banner](../includes/banner.md)]


Ten artykuł zawiera omówienie mechanizmu blokowania zapasów, który jest częścią procesu kontroli jakości w programie Microsoft Dynamics 365 for Finance and Operations Enterprise Edition. Używając blokowania, można zapobiec przetwarzaniu i zużywaniu zapasów.

Pozycje magazynowe można blokować w następujący sposób:
-   Ręcznie
-   Tworząc zlecenie kontroli jakości
-   Za pomocą procesu, który generuje zlecenia kontroli jakości
-   przez blokowanie stanu zapasów

## <a name="blocking-items-manually"></a>ręczne blokując towary
Ilość towaru można zablokować przez utworzenie transakcji na stronie **Blokowanie zapasów**. Ręcznie można zablokować jedynie pozycje dostępne na stanie w magazynie. Dla ilości zablokowanych ręcznie należy rozważyć, czy oczekiwane przychody powinny znajdować się w działaniach planowania jako oczekiwana ilość zapasów na stanie. Oczekiwane przyjęcia to zablokowane towary, które według przewidywań po inspekcji będą dostępne jako zapasy na stanie. Można zachować oczekiwaną datę. Domyślnie opcja **Oczekiwane przyjęcia** jest zaznaczona dla towarów, które są zablokowane za pomocą zlecenia kontroli jakości. Można anulować blokowanie ilości ręcznie blokowanych przez usunięcie transakcji na stronie **Blokowanie zapasów**.

## <a name="blocking-items-by-creating-a-quality-order"></a>Blokując towary poprzez tworzenie zlecenia kontroli jakości
Można określić elementy, które muszą być skontrolowane, przez utworzenie zlecenia kontroli jakości na stronie **zleceń kontroli jakości**. Po utworzeniu zlecenia kontroli jakości, określona ilość towaru jest zablokowana. Plan pobierania próbek skojarzony ze zleceniem kontroli jakości kontroluje ilość towaru, który ma być sprawdzany, nie ilość, która jest zablokowana. Niezależnie od ilości, która zostanie wysłana do inspekcji, jak określono w planie pobierania próbek, ilość towaru wprowadzona w zleceniu kontroli jakości jest ilością, która zostaje zablokowana.

## <a name="blocking-items-by-using-a-process-that-generates-a-quality-order"></a>Blokując towary za pomocą procesu, który generuje zlecenia kontroli jakości.
Jeśli w procesie kontroli jakości określono konieczność kontroli pozycji, ilość towaru zostanie automatycznie zablokowana. Tak więc podczas automatycznego generowania zlecenia kontroli jakości plan próbkowania towaru skojarzony z zamówieniem kontroli jakości określa ilość towarów, która jest zablokowana i ilość towarów, które mają zostać sprawdzone. W przypadku zaznaczenia opcji **Pełne blokowanie** na stronie **Kontrola wyrywkowa towarów**, całkowita ilość, na przykład, w wierszu zamówienia zakupu jest zablokowana podczas inspekcji, niezależnie od ilości kontroli wyrywkowej towarów.
### <a name="example"></a>Przykład

W poniższym przykładzie generowane jest zlecenie kontroli jakości podczas księgowania dokumentu dostawy zamówienia zakupu. Na stronie **Powiązania jakości** określono, że księgowanie dokumentu dostawy zamówienia zakupu jest określone jako proces, który aktywuje zlecenia kontroli jakości.

|Ustawienia                                                                     |Akcja użytkownika                 |Wynik             |
|--------------------------------------------------------------------------|----------------------------|-------------------|
| Skojarzenie jakości określa, że przy księgowaniu dokumentu dostawy zamówienia zakupu musi zostać wygenerowane zlecenie kontroli jakości. Ustawienia kontroli wyrywkowej towarów zlecenia kontroli jakości określa, że musi zostać skontrolowane 10% ilości w wierszu zamówienia zakupu. Co więcej, przy zaznaczonym polu wyboru **Pełne blokowanie** ustawienie pobierania próbek wskazuje, że podczas inspekcji, niezależnie od ilości, która zostanie wysłana do inspekcji, należy zablokować pełną ilość w wierszu zamówienia zakupu. | Dokumentu dostawy zostaje zaksięgowany. | Zlecenie kontroli jakości zostało wygenerowane. 10% ilości towaru w zamówieniu zakupu jest wysyłane do inspekcji. Całkowita ilość wiersza zamówienia zakupu jest zablokowana. |

## <a name="blocking-items-by-using-inventory-status-blocking"></a>przez blokowanie towarów za pomocą blokowania stanu magazynu
Można określić, które stany zapasów powodują blokowanie, za pomocą parametru **Blokowania zapasów** na stronie **Stany zapasów**. Stanów zapasów nie można używać jako stanów blokowania dla zleceń produkcyjnych, zamówień sprzedaży, zamówień przeniesienia, transakcji wychodzących i integracji projektu. W przypadku pracy wychodzącej należy użyć towarów z dostępnym stanem zapasów. Jeśli masz towary o stanie **uszkodzone** i zostało dla nich uruchomione planowanie główne, pozycje te zostaną uznane za brakujące, a zapasy są uzupełniane automatycznie.



<a name="see-also"></a>Informacje dodatkowe
--------

[Tworzenie i obsługa blokowania zapasów (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/create-and-maintain-an-inventory-blocking/)

[Procesy zarządzania jakością](quality-management-processes.md)

[Sprawdzenie jakości towarów (przewodnik po zadaniu)](https://ax.help.dynamics.com/en/wiki/inspect-the-quality-of-goods/)




