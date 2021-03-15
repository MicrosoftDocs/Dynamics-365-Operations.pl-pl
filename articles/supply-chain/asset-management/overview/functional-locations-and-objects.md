---
title: Lokalizacje czynności konserwacyjnych i składniki majątku
description: W tym temacie opisano lokalizacje funkcjonalne i składniki majątku w Zarządzaniu składnikami majątku. Zarządzanie składnikami majątku to zaawansowany moduł do zarządzania zasobami i zadaniami konserwacyjnymi w Dynamics 365 Supply Chain Management.
author: josaw1
manager: tfehr
ms.date: 06/24/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CatProcureCatalogEdit, CatProcureCatalogListPage
audience: Application User
ms.reviewer: kamaybac
ms.custom: 2214
ms.assetid: 2f3e0441-414d-402b-b28b-7ab0d650d658
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f93a68f19b0b952eb2964b404bb957865c625cd
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018053"
---
# <a name="functional-locations-and-assets"></a>Lokalizacje czynności konserwacyjnych i składniki majątku

[!include [banner](../../includes/banner.md)]

 

W tym temacie opisano lokalizacje funkcjonalne i składniki majątku w Zarządzaniu składnikami majątku. Zarządzanie składnikami majątku to zaawansowany moduł do zarządzania zasobami i zadaniami konserwacyjnymi w Dynamics 365 Supply Chain Management.

## <a name="overview"></a>Przegląd

Moduł Zarządzanie składnikami majątku jest bezproblemowo integrowany z kilkoma modułami w innych aplikacjach Finance and Operations. Na poniższej ilustracji przedstawiono interfejsy z innymi modułami.

![Diagram przedstawiający sposób współdziałania modułu Zarządzanie składnikami majątku z innymi modułami](media/01-overview-image.png)

Zarządzanie składnikami majątku umożliwia efektywne zarządzanie i wykonywanie wszystkich zadań związanych z zarządzaniem i obsługą wielu typów urządzeń w firmie. Te urządzenia obejmują maszyny, urządzenia produkcyjne i pojazdy. Zarządzanie składnikami majątku również wspiera rozwiązania w wielu branżach.

Poniższa ilustracja przedstawia omówienie głównych funkcji dostępnych w module Zarządzanie składnikami majątku.

![Diagram przedstawiający główną funkcjonalność modułu Zarządzanie składnikami majątku](media/02-overview-image.png)

## <a name="functional-locations-and-assets"></a>Lokalizacje czynności konserwacyjnych i składniki majątku

Lokalizacje czynności konserwacyjnych służą do zarządzania zasobami w lokalizacjach. To zarządzanie obejmuje śledzenie kosztów aktywów w lokalizacjach czynności konserwacyjnych. Lokalizacje czynności konserwacyjnych są uporządkowane hierarchicznie, a lokalizacje mogą mieć Podlokalizacje. Struktura lokalizacji czynności konserwacyjnych jest statyczna. Innymi słowy, lokalizacje nie mogą zmieniać miejsca. Składniki majątku mogą być instalowane w lokalizacjach czynności konserwacyjnych i, zgodnie z wymaganiami, mogą być instalowane później w innych lokalizacjach czynności konserwacyjnych.

Koszty składników majątku zawsze są zgodne z lokalizacją składnika majątku. Innymi słowy jeśli zasób jest instalowany w nowej lokalizacji czynności konserwacyjnych, zasób automatycznie używa wymiarów finansowych, które są powiązane z nową lokalizacją czynności konserwacyjnych. W związku z tym koszty składnika majątku są zawsze związane z lokalizacją czynności konserwacyjnych, na której jest aktualnie zainstalowany składnik majątku. Ta automatyczna obsługa wymiarów finansowych pomaga zagwarantować całkowite śledzenie kosztów, gdy Twoja firma kontroluje i raportuje lokalizacje czynności konserwacyjnych.

Sposób budowania hierarchii lokalizacji czynności konserwacyjnych zależy od wymagań firmy w zakresie utrzymywania wewnętrznego sprzętu lub obsługi sprzętu klienta. Na poniższej ilustracji przedstawiono przykład lokalizacji czynności konserwacyjnych, które są oparte na lokalizacjach geograficznych.

![Diagram przedstawiający lokalizacje czynności konserwacyjnych na podstawie lokalizacji geograficznych](media/03-overview-image.png)

Na poniższej ilustracji przedstawiono przykład lokalizacji czynności konserwacyjnych, które są oparte na klientach.

![Diagram przedstawiający lokalizacje czynności konserwacyjnych na podstawie klientów](media/04-overview-image.png)


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]