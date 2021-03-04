---
title: Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych
description: W tym temacie opisano sposób dodawania pól do skoroszytu programu Microsoft Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 11/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: ''
ms.openlocfilehash: 443e5e9931498799f9a96fc55c6e5d5c9f6750c6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980413"
---
# <a name="add-fields-to-an-excel-workbook-to-edit-retail-transactions"></a>Dodawanie pól do skoroszytu programu Excel w celu edytowania transakcji detalicznych

[!include [banner](../includes/banner.md)]

W tym temacie opisano sposób dodawania pól do skoroszytu programu Microsoft Excel w celu umożliwienia edycji transakcji detalicznych w rozwiązaniu Microsoft Dynamics 365 Commerce.

## <a name="overview"></a>Omówienie

Podczas generowania pliku programu Excel do edycji transakcji detalicznych plik zostaje wypełniony określonymi polami domyślnymi. Jeśli pole, które musi zostać zaktualizowane, nie jest domyślnie widoczne w wygenerowanym pliku programu Excel, można je dodać.

## <a name="add-fields-to-a-worksheet-in-an-excel-workbook"></a>Dodawanie pól do arkusza skoroszytu programu Excel

Aby dodać pola do skoroszyt programu Excel, by móc edytować transakcje sprzedaży detalicznej, wykonaj kroki opisane poniżej.

1. Pobierz i otwórz plik programu Excel ze strony **Zestawienia** lub **Transakcje sprzedaży detalicznej** albo kafelka **Weryfikacje transakcji zakończone niepowodzeniem** w obszarze roboczym **Finanse sklepu**.
1. Wybierz **Projekt**.
1. Zaznacz symbol ołówka dla żądanej tabeli, a następnie znajdź na liście dostępnych pól pole, które chcesz dodać, i wybierz je.
1. Wybierz opcję **Dodaj**, a następnie opcję **Aktualizuj**. Kolejność pól można zmieniać.
1. Po zakończeniu aktualizacji wybierz opcję **Odśwież**, aby pobrać dane dla nowej kolumny.

Na tym etapie nowe pole oraz dane dla niego powinny być dostępne do edycji w programie Excel.

## <a name="additional-resources"></a>Dodatkowe zasoby

[Edycja i przeprowadzanie inspekcji transakcji kasowych i przeniesienia oraz zarządzania gotówką](edit-cash-trans.md)

[Edycja i przeprowadzanie inspekcji transakcji zamówień online i asynchronicznych zamówień odbiorcy](edit-order-trans.md)

[Edytowanie wymiarów finansowych dla transakcji sprzedaży detalicznej](edit-financial-dim.md)

[Tworzenie skoroszytu programu Excel w celu edytowania transakcji detalicznych](create-excel-edit.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]