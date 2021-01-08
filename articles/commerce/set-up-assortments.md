---
title: Konfigurowanie asortymentu
description: W tym artykule opisano, co jest asortyment, i wyjaśniono, jak konfigurować asortymenty w programie Dynamics 365 Commerce.
author: jblucher
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
ms.search.form: RetailAssortmentDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 15811
ms.assetid: d2580048-e798-4b33-85f9-d1bad7d262fc
ms.search.region: global
ms.search.industry: Retail
ms.author: jeffbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.openlocfilehash: 26614d319453041177e8072793f09f52ebfd51fc
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415040"
---
# <a name="set-up-assortments"></a>Konfigurowanie asortymentów

[!include [banner](includes/banner.md)]

W tym artykule opisano, co jest asortyment, i wyjaśniono, jak konfigurować asortymenty w programie Dynamics 365 Commerce.

Asortyment jest zbiorem pokrewnych produktów, które można przypisać do kanału handlu, takich jak sklep tradycyjny (stacjonarny) lub sklep internetowy. Asortymenty służą do identyfikacji produktów, które są dostępne w każdym sklepie. Asortyment może zawierać kategorie produktów. W związku z tym wszystkie produkty, które są przypisane do wybranej kategorii, znajdują się w asortymencie. Asortyment może również uwzględniać określone produkty i ich warianty. Konfigurując asortyment można jednocześnie przypisać tysiące produktów do kanałów w dowolnej kombinacji wymaganej w sklepach. Można skonfigurować dowolną liczbę asortymentów produktów. Każdy produkt można włączyć do jednego lub większej liczby asortymentów, a każdy z asortymentów można przypisać do jednego lub większej liczby kanałów. Na przykład można zdefiniować jeden asortyment, który uwzględnia bazowy zestaw produktów. Wszystkie sklepy otrzymają ten sam asortyment. Następnie można zdefiniować inny asortyment zawierający tylko duży sprzęt sportowy. Ten asortyment trafi tylko do większych sklepów. Na poniższym diagramie pokazano, jak można przypisać produkty do asortymentu, i jak przypisać asortymenty do kanałów.

![Asortyment produktów — relacje](./media/assortments_relationship.gif)

## <a name="prerequisites"></a>Wymagania wstępne

Aby można było skonfigurować asortyment i przypisać go do kanału handlu, należy wykonać następujące zadania.

| Zadanie                              | Opis |
|-----------------------------------|-------------|
| Konfigurowanie kanału.          | Kanały obejmują sklep tradycyjny, internetowy i internetowy serwis sprzedażowy. Należy skonfigurować co najmniej jeden kanał i skonfigurować opcje dla sklepu. Asortymenty są przypisane do sklepów w celu identyfikacji produktów w danym sklepie. |
| Tworzenie hierarchii organizacyjnej. | Po skonfigurowaniu kanałów handlu dla organizacji należy skonfigurować hierarchię organizacyjną, odzwierciedlającą strukturę organizacji kanałów. Hierarchia organizacyjna może służyć np. do obsługi asortymentów, uzupełnienia lub zgłoszenia. Dodając kanały do hierarchii organizacyjnej, można przypisać asortymenty do grup sklepów. Zamiast przypisywania asortymentu oddzielnie do każdego sklepu, asortyment jest przypisywany do węzła organizacji wysokiego poziomu. Następnie przy każdym dodaniu nowego kanału do węzła wysokiego poziomu organizacji, kanał ten automatycznie dziedziczy wszystkie asortymenty, które zostały przypisane do wyższego poziomu węzła organizacji. Asortymenty można przypisać tylko do kanałów, które są uwzględniane w hierarchii organizacyjnej przypisanego celu **asortymentu sprzedaży**. |
| Definiowanie produktów.                  | Przed dodaniem produktów do asortymentu, należy dodać je w usłudze Commerce. Istnieje możliwość ręcznego dodawania produktów lub można je zaimportować od dostawcy. Po dodaniu produktów można je zwolnić do firmy. Tylko zatwierdzone produkty, które zostały zwolnione dla firmy mogą być dostępne dla kanałów. Produkty, które nie zostały jeszcze zwolnione do firmy, mogą być dodawane do asortymentu, a asortyment może zostać zatwierdzony. Ale przed zwolnieniem produktów do firmy nie można ich udostępnić w kanałach. |
| Ustawianie hierarchii kategorii.      | Podczas tworzenia produktów handlu można je grupować i klasyfikować za pomocą funkcji hierarchii kategorii. Można utworzyć jedną hierarchię podstawową do grupowania i klasyfikowania wszystkich produktów, które można dystrybuować w kanałach. Można także tworzyć osobne hierarchie kategorii uzupełniającej, do grupowania lub kategoryzowania produktów do celów specjalnych, takich jak promocje lub asortymenty. Za pomocą hierarchii kategorii można przypisać wszystkie produkty z określonej kategorii do asortymentu. Wszystkie produkty, które są dodawane do kategorii uwzględnionej w asortymencie są automatycznie uwzględnione w asortymencie. Następnie podczas następnego uruchomienia harmonogramu asortymentu handlu, produkty te stają się dostępne dla kanałów do asortymentu. |

## <a name="setting-up-an-assortment"></a>Konfigurowanie asortymentu

Po spełnieniu wymagań wstępnych można tworzyć asortyment i przypisywać go w kanałach. Aby skonfigurować asortyment, należy wykonać następujące zadania:

1. Tworzenie nowego asortymentu lub skopiowanie istniejącego.
2. Wybierz kanały grup wysokiego poziomu kanałów, których dotyczy asortyment.
3. Dodaj kategorie produktu, pojedyncze produkty lub ich warianty do asortymentu. Można uwzględnić wszystkie produkty w konkretnej kategorii lub można wykluczyć wybrane produkty z kategorii, która jest uwzględniona w asortymencie.
4. Opublikuj asortyment. Po opublikowaniu asortymentu harmonogram Asortymenty jest uruchamiany automatycznie. Ten proces generuje listę produktów. Po zakończeniu tego procesu, produkty stają się dostępne dla kanałów przypisanych do asortymentu produktów. Jeśli wprowadzono zmiany asortymentu, który został opublikowany lub kanałów przypisanych do asortymentu, należy zaktualizować asortyment. Do aktualizacji asortymentu, gdy zostaną wprowadzone zmiany, można uruchomić zadanie przetwarzania wsadowego asortymentu.
