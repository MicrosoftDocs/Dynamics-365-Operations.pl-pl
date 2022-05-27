---
title: Zmienianie lub usuwanie oryginalnego międzyfirmowego zamówienia sprzedaży
description: W tym temacie wyjaśniono, jak zmieniać i usuwać funkcje oryginalnego zamówienia sprzedaży
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: cfacd1710aa5812230395409f1dd7c2e882faa9f
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673754"
---
# <a name="change-or-delete-an-original-intercompany-sales-order"></a>Zmienianie lub usuwanie oryginalnego międzyfirmowego zamówienia sprzedaży

[!include [banner](../../includes/banner.md)]

Po zmianie zamówienia sprzedaży zmiany są automatycznie synchronizowane zarówno z odpowiednim międzyfirmowym zamówieniem zakupu, jak i międzyfirmowym zamówieniem sprzedaży.

> [!NOTE]
> Zamówienia zakupu dla zewnętrznych dostawców nie zmieniają się na skutek wprowadzonych zmian; tak samo nie zmieniają się wiersze oryginalnego zamówienia połączone z wierszami zamówienia zakupu dla zewnętrznych dostawców.

W poniższej tabeli podsumowano zmiany, które można wprowadzić i oczekiwane wyniki.

| Operacja | Wynik |
|---|---|
| Usuń &nbsp;&nbsp;oryginalne zamówienie &nbsp;&nbsp;sprzedaży. | Powiązane międzyfirmowe zamówienie zakupu i międzyfirmowe zamówienie sprzedaży są również usuwane. Zamówienia sprzedaży nie można usunąć, jeśli osiągnęło stan **Lista pobrania** lub późniejszy etap procesu. |
| Usunąć wiersz oryginalnego zamówienia sprzedaży. | Usuwany jest także odpowiedni wiersz międzyfirmowego zamówienia zakupu oraz wiersz międzyfirmowego zamówienia sprzedaży. Wiersza zamówienia sprzedaży nie można usunąć, jeśli osiągnęło stan **Lista pobrania** lub późniejszy etap procesu. |
| Dodać nowy wiersz sprzedaży do oryginalnego zamówienia sprzedaży. | Nowy wiersz sprzedaży tworzony jest zarówno na międzyfirmowym zamówieniu zakupu, jak i międzyfirmowym zamówieniu sprzedaży. |
| Zmienić ilość w wierszy oryginalnego zamówienia sprzedaży. | Ilość jest synchronizowana zarówno z wierszem międzyfirmowego zamówienia zakupu, jak i z międzyfirmowym wierszem zamówienia sprzedaży. Kwota netto jest przeliczana na wszystkich zamówieniach. |
| Wyłączyć dostawę bezpośrednią na oryginalnym zamówieniu sprzedaży. | Pola **Dostawa bezpośrednia** nie można zmienić na oryginalnym zamówieniu sprzedaży, jeśli wiersz zamówienia międzyfirmowe zamówienie sprzedaży osiągnął minimalny stan **lista pobrania**, **zamówienie wyjścia** lub **arkusz listy pobrania**. Adres dostawy w międzyfirmowym zamówieniu zakupu zostanie zmieniony na standardowy adres dostawy (standardowy adres dostawy zamówienia zakupu). Ponadto wiersze międzyfirmowego zamówienia zakupu są zmieniane na standardowy adres dostawy dla wierszy. Oba adresy są synchronizowane z międzyfirmowym zamówieniem sprzedaży oraz wierszami zamówienia. Typ dostawy we wszystkich wierszach oryginalnego zamówienia sprzedaży jest zmieniany na **Brak**, a pole jest synchronizowane z wierszami międzyfirmowego zamówienia zakupu. Nie ma to wpływu na zamówienia zakupu dla dostawców zewnętrznych; podobnie jak oryginalne wiersze sprzedaży, które są połączone z wierszami zamówienia zakupu dla dostawców zewnętrznych. Aktualizowana jest data dostawy na międzyfirmowym zamówieniu zakupu, w wierszach – a także żądana data przyjęcia/dostarczenia na międzyfirmowym zamówieniu sprzedaży i w wierszach. |
| Włączyć dostawę bezpośrednią na oryginalnym zamówieniu sprzedaży. | Pola **Dostawa bezpośrednia** nie można zmienić na oryginalnym zamówieniu sprzedaży, jeśli wiersz zamówienia międzyfirmowe zamówienie sprzedaży osiągnął minimalny stan **lista pobrania**, **zamówienie wyjścia** lub **arkusz listy pobrania**. Adres dostawy w międzyfirmowym zamówieniu zakupu zostanie zmieniony na adres dostawy z oryginalnego zamówienia sprzedaży i zsynchronizowany z międzyfirmowym zamówieniem sprzedaży. Typ dostawy we wszystkich wierszach oryginalnego zamówienia sprzedaży jest zmieniany na **Dostawa bezpośrednia**, a pole jest synchronizowane z wierszami międzyfirmowego zamówienia zakupu. Adres dostawy we wszystkich wierszach oryginalnego zamówienia sprzedaży jest zsynchronizowany z wierszami międzyfirmowego zamówienia zakupu oraz z wierszami międzyfirmowego zamówienia sprzedaży. Aktualizowana jest data dostawy na międzyfirmowym zamówieniu zakupu, w wierszach – a także żądana data przyjęcia/dostarczenia na międzyfirmowym zamówieniu sprzedaży i w wierszach. |
| Dodać uwagę do nagłówka i wierszy oryginalnego zamówienia sprzedaży. | Uwaga jest kopiowana do międzyfirmowego zamówienia zakupu oraz do międzyfirmowego zamówienia sprzedaży. |
| Zmienić lub usunąć uwagę. | Jeśli zmienisz lub usuniesz notatkę, odpowiednia notatka w międzyfirmowym zamówieniu zakupu i międzyfirmowym zamówieniu sprzedaży zostanie odpowiednio zmieniona lub usunięta. |

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
