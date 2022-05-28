---
title: Relacje przedmiotów serwisu
description: Można utworzyć relacje przedmiotów serwisu oraz umowę serwisową lub zlecenie serwisowe.
author: sorenva
ms.date: 02/21/2018
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: SMAServiceObjectRelation
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: sorenand
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 831db29589826904666049edbc8be0c38e1d02a5
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8676643"
---
# <a name="service-object-relations"></a>Relacje przedmiotów serwisu 

[!include [banner](../includes/banner.md)]

Można utworzyć relacje przedmiotów serwisu oraz umowę serwisową lub zlecenie serwisowe. Podczas tworzenia relacji przedmiot serwisu łączy się z umową serwisową lub zleceniem serwisowym.

Po utworzeniu relacji można połączyć przedmiot serwisu z dowolnymi wierszami umowy serwisowej lub zlecenia serwisowego.

## <a name="template-boms"></a>Szablony BOM

Można także określić szablon BOM dla relacji przedmiotu. Szablon BOM dotyczy przedmiotu serwisu. W przypadku wymiany części przedmiotu serwisu w czasie wizyty serwisowej można zarejestrować na liście BOM usługi serwisowej przy użyciu formularza Przedmioty serwisu.

## <a name="example"></a>Przykład

Tworzona jest umowa serwisowa dotycząca serwisu dwóch wind w siedzibie klienta.
Umowa serwisowa ma identyfikator ID SAL-001.

Windy skonfigurowano w formularzu Przedmioty serwisu jako obiekty EL-S/1000 i EL-L/1000.

Przedmioty serwisu EL-S/1000 i EL-L/1000 należy połączyć z umową serwisową.

Zmiany dotyczące przedmiotu serwisu zostaną zarejestrowane w BOM podczas wymiany części przedmiotu, więc lista BOM usługi zostanie połączona z relacją przedmiotu serwisu zgodnie z następującą tabelą.

| Przedmiot serwisu | Relacja — Umowa serwisowa | BOM serwisu   |
|----------------|------------------------------|---------------|
| EL-S/1000      | ID SAL-001                   | BOM-EL-S/1000 |
| EL-L/1000      | ID SAL-001                   | BOM-EL-L/1000 |

Dla umowy występują relacje przedmiotów serwisu, więc można utworzyć wiersze umowy serwisowej zawierające te przedmioty, jak pokazano w poniższej tabeli.

| Typ transakcji | Kategoria           | Przedmiot serwisu |
|------------------|--------------------|----------------|
| Godzina             | Kontrola         | EL-S/1000      |
| Godzina             | Czyszczenie skrzynki przekładniowej  | EL-S/1000      |
| Element             | Materiały czyszczące | EL-S/1000      |
| Godzina             | Kontrola         | EL-L/1000      |
| Godzina             | Czyszczenie skrzynki przekładniowej   | EL-L/1000      |
| Element             | Materiały czyszczące | EL-L/1000      |

W czasie wizyty serwisowej należy wymienić skrzynkę przekładniową windy EL-S/1000. Aby wymienić część przedmiotu, należy uzyskać dostęp do Konstruktora BOM, używając relacji przedmiotu serwisu, która została skonfigurowana dla bieżącej umowy serwisowej.

Uzyskiwanie dostępu do Konstruktora BOM przy użyciu relacji przedmiotu serwisu

1. Umowy serwisowe
2. Kliknij dwukrotnie umowę serwisową lub kliknij opcję Umowa serwisowa, aby utworzyć umowę serwisową.
3. Kliknij kartę Ustawienia.
4. Kliknij opcję Przedmioty serwisu, aby dołączyć szablon BOM do umowy serwisowej.
5. W formularzu Przedmioty serwisu kliknij opcję Projektant, aby otworzyć formularz Projektant i w nim zmodyfikować szablon BOM.

## <a name="automatically-created-service-orders"></a>Zlecenia serwisowe tworzone automatycznie

W przypadku automatycznego tworzenia zleceń serwisowych dotyczących umowy serwisowej relacje przedmiotów serwisu w umowie znajdują się także w tworzonych zleceniach serwisowych.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]