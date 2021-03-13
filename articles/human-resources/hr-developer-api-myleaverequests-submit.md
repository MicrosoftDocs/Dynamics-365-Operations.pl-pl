---
title: Przesyłanie wniosku o urlop do przepływu pracy
description: W rozwiązaniu Microsoft Dynamics 365 Human Resources można skorzystać z interfejsu API przesyłania MyLeaveRequests w celu przesłania wniosku urlopowego do przepływu pracy.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 51be70edbe1439340377fd01b9760d49d3a75348
ms.sourcegitcommit: 18e626c49ccfdb12c1484b985e3a275e51f61320
ms.translationtype: HT
ms.contentlocale: pl-PL
ms.lasthandoff: 02/04/2021
ms.locfileid: "5115519"
---
# <a name="submit-a-leave-request-to-workflow"></a><span data-ttu-id="74380-103">Przesyłanie wniosku o urlop do przepływu pracy</span><span class="sxs-lookup"><span data-stu-id="74380-103">Submit a leave request to workflow</span></span>

<span data-ttu-id="74380-104">W rozwiązaniu Microsoft Dynamics 365 Human Resources można skorzystać z interfejsu API przesyłania MyLeaveRequests w celu przesłania wniosku urlopowego do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="74380-104">In Microsoft Dynamics 365 Human Resources, you can use the MyLeaveRequests submit() application programming interface (API) to submit a leave request to workflow.</span></span> <span data-ttu-id="74380-105">Ten interfejs API jest udostępniany jako akcja w jednostce protokołu OData o nazwie MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="74380-105">This API is exposed as an action on the MyLeaveRequests OData entity.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74380-106">Wymagania wstępne</span><span class="sxs-lookup"><span data-stu-id="74380-106">Prerequisites</span></span>

<span data-ttu-id="74380-107">Wniosek urlopowy musi zostać zapisany w bazie danych i być możliwy do pobrania za pośrednictwem jednostki MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="74380-107">The leave request must be saved in the database and must be retrievable through the MyLeaveRequests entity.</span></span>

## <a name="permissions"></a><span data-ttu-id="74380-108">Uprawnienia</span><span class="sxs-lookup"><span data-stu-id="74380-108">Permissions</span></span>

<span data-ttu-id="74380-109">Do wywołania tego interfejsu API jest wymagane jedno z poniższych uprawnień.</span><span class="sxs-lookup"><span data-stu-id="74380-109">One of the following permissions is required to call this API.</span></span> <span data-ttu-id="74380-110">Aby uzyskać więcej informacji na temat uprawnień i ich wybierania, zobacz [Uwierzytelnianie](hr-developer-api-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="74380-110">For more information about permissions and how to select them, see [Authentication](hr-developer-api-authentication.md).</span></span>

| <span data-ttu-id="74380-111">Typ uprawnienia</span><span class="sxs-lookup"><span data-stu-id="74380-111">Permission type</span></span>                    | <span data-ttu-id="74380-112">Uprawnienia (od najmniej uprzywilejowanych do najbardziej uprzywilejowanych)</span><span class="sxs-lookup"><span data-stu-id="74380-112">Permissions (from least privileged to most privileged)</span></span> |
|------------------------------------|--------------------------------------------------------|
| <span data-ttu-id="74380-113">Delegowane (konto służbowe lub uczelniane)</span><span class="sxs-lookup"><span data-stu-id="74380-113">Delegated (work or school account)</span></span> | <span data-ttu-id="74380-114">user\_impersonation</span><span class="sxs-lookup"><span data-stu-id="74380-114">user\_impersonation</span></span>                                    |

## <a name="https-request"></a><span data-ttu-id="74380-115">Żądanie HTTPS</span><span class="sxs-lookup"><span data-stu-id="74380-115">HTTPS request</span></span>

<!-- { "blockType": "ignored" } -->
```HTTP
POST https://{cluster}.hr.talent.dynamics.com/namespaces/{namespace_guid}/data/MyLeaveRequests(RequestId='{requestId}', LeaveType='{leaveType}', LeaveDate={leaveDate}, dataAreaId={dataArea})/Microsoft.Dynamics.DataEntities.submit?cross-company=true
```

<span data-ttu-id="74380-116">Żądanie jest zgodne ze standardami protokołu OData.</span><span class="sxs-lookup"><span data-stu-id="74380-116">The request conforms to OData standards.</span></span> <span data-ttu-id="74380-117">Parametry {requestId}, {leaveType}, {leaveDate} i {dataArea} odwołują się do pól tworzących zbiorczy klucz naturalny jednostki MyLeaveRequests.</span><span class="sxs-lookup"><span data-stu-id="74380-117">The {requestId}, {leaveType}, {leaveDate}, and {dataArea} parameters refer to the fields that make up the composite natural key for the MyLeaveRequests entity.</span></span>

> [!NOTE]
> <span data-ttu-id="74380-118">Pola jednostki MyLeaveRequests odwołują się do pojedynczego wiersza we wniosku urlopowym, ale wywołanie interfejsu API przesyłania spowoduje przesłanie całego wniosku urlopowego (wszystkich wierszy) do przepływu pracy.</span><span class="sxs-lookup"><span data-stu-id="74380-118">While the fields for the MyLeaveRequests entity refer to an individual line in the leave request, calling the submit API will submit the entire leave request (all lines) to workflow.</span></span>

### <a name="request-headers"></a><span data-ttu-id="74380-119">Nagłówki żądań</span><span class="sxs-lookup"><span data-stu-id="74380-119">Request headers</span></span>

| <span data-ttu-id="74380-120">Nagłówek</span><span class="sxs-lookup"><span data-stu-id="74380-120">Header</span></span>         | <span data-ttu-id="74380-121">Value</span><span class="sxs-lookup"><span data-stu-id="74380-121">Value</span></span>                     |
|----------------|---------------------------|
| <span data-ttu-id="74380-122">Autoryzacja</span><span class="sxs-lookup"><span data-stu-id="74380-122">Authorization</span></span>  | <span data-ttu-id="74380-123">Okaziciel {token} (wymagana)</span><span class="sxs-lookup"><span data-stu-id="74380-123">Bearer {token} (required)</span></span> |
| <span data-ttu-id="74380-124">Typ zawartości</span><span class="sxs-lookup"><span data-stu-id="74380-124">Content-Type</span></span>   | <span data-ttu-id="74380-125">application/json</span><span class="sxs-lookup"><span data-stu-id="74380-125">application/json</span></span>          |

### <a name="request-body"></a><span data-ttu-id="74380-126">Treść wniosku</span><span class="sxs-lookup"><span data-stu-id="74380-126">Request body</span></span>

<span data-ttu-id="74380-127">W tej metodzie nie należy podawać treści wniosku.</span><span class="sxs-lookup"><span data-stu-id="74380-127">Don't supply a request body for this method.</span></span>

### <a name="response"></a><span data-ttu-id="74380-128">Odpowiedź</span><span class="sxs-lookup"><span data-stu-id="74380-128">Response</span></span>

<span data-ttu-id="74380-129">Pomyślna odpowiedź zawsze ma treść **204 Brak zawartości**.</span><span class="sxs-lookup"><span data-stu-id="74380-129">A successful response is always a **204 No Content** response.</span></span>

<span data-ttu-id="74380-130">Nieautoryzowane obiekty wywołujące otrzymają odpowiedź **401 Nieautoryzowany** lub **403 Zabroniony**.</span><span class="sxs-lookup"><span data-stu-id="74380-130">Unauthorized callers will receive a **401 Unauthorized** or a **403 Forbidden** response.</span></span>

<span data-ttu-id="74380-131">Jeśli przesyłanie się nie powiedzie (na przykład z powodu nieudanej weryfikacji), odpowiedzią będzie **500 Błąd serwera**, a treść odpowiedzi będzie zawierała obiekt JSON z dalszymi szczegółami.</span><span class="sxs-lookup"><span data-stu-id="74380-131">If submission is unsuccessful (because of validation, for example), the response will be a **500 Server Error**, and the response body will include a JSON object with further details.</span></span>

## <a name="example"></a><span data-ttu-id="74380-132">Przykład</span><span class="sxs-lookup"><span data-stu-id="74380-132">Example</span></span>

```http
POST https://aos-rts-sf-550e5c091f6-prod-westus2.hr.talent.dynamics.com/namespaces/b2eb8003-334f-4a84-ab63-edbe23569090/data/MyLeaveRequests(RequestId='USMF-000065', LeaveType='Vacation', LeaveDate=2019-10-04T12:00:00Z, dataAreaId='USMF')/Microsoft.Dynamics.DataEntities.submit
```

```json
{
  "error": {
    "code": "",
    "message": "An error has occurred.",
    "innererror": {
      "message": "Exception occurred while executing action submit on Entity MyLeaveRequest: The request would put the 'Vacation' balance below the allowed minimum balance on 9/10/2019.",
      "type": "System.InvalidOperationException",
      "stacktrace": "   at Microsoft.Dynamics.Platform.Integration.Services.OData.Action.ActionInvokable.Invoke()   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateProcessor.ActionInvocation(ChangeOperationContext context, ActionInvokable action)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.<>c__DisplayClass13_0.<ScheduleInvokable>b__0(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActionsInCompanyContext(IEnumerable`1 actionList, ChangeOperationContext operationContext)\r\n   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.ChangeInfo.ExecuteActions(ChangeOperationContext context)   at Microsoft.Dynamics.Platform.Integration.Services.OData.Update.UpdateManager.SaveChanges()   at Microsoft.Dynamics.Platform.Integration.Services.OData.AxODataDelegatingHandler.<SaveChangesAsync>d__3.MoveNext()"
    }
  }
}
```

## <a name="validation-and-error-messages"></a><span data-ttu-id="74380-133">Weryfikacja i komunikaty o błędach</span><span class="sxs-lookup"><span data-stu-id="74380-133">Validation and error messages</span></span>

<span data-ttu-id="74380-134">W ramach wywołania interfejsu API przesyłania moduł Human Resources przeprowadza weryfikację logiki biznesowej przed rozpoczęciem przesyłania, co gwarantuje, że wniosek urlopowy będzie w prawidłowym stanie do przesłania.</span><span class="sxs-lookup"><span data-stu-id="74380-134">As part of the call to the submit API, Human Resources performs business logic validation before submission, which ensures the leave request is in a valid state for submission.</span></span> <span data-ttu-id="74380-135">W razie niepowodzenia sprawdzania poprawności mogą się w odpowiedzi pojawić następujące komunikaty o błędach:</span><span class="sxs-lookup"><span data-stu-id="74380-135">The possible error messages you may receive in the response if validations fail are:</span></span>

 - <span data-ttu-id="74380-136">Zaakceptowanie wniosku spowodowałaby zmniejszenie salda „{LeaveTypeId}” do poziomu niższego niż dozwolone saldo minimalne na dzień {date}.</span><span class="sxs-lookup"><span data-stu-id="74380-136">The request would put the '{LeaveTypeId}' balance below the allowed minimum balance on {date}.</span></span>
 - <span data-ttu-id="74380-137">Nie można przesłać wniosku urlopowego w stanie Ukończone.</span><span class="sxs-lookup"><span data-stu-id="74380-137">Time off request in Completed state cannot be submitted.</span></span>
 - <span data-ttu-id="74380-138">Nie można przesłać lub zapisać wniosku, ponieważ nie wprowadzono żadnych zmian.</span><span class="sxs-lookup"><span data-stu-id="74380-138">Unable to submit or save request as no changes have been made.</span></span> <span data-ttu-id="74380-139">Dodaj lub zaktualizuj ilość albo typ urlopu, a następnie spróbuj ponownie.</span><span class="sxs-lookup"><span data-stu-id="74380-139">Add or update the amount or the leave type and try again.</span></span>
 - <span data-ttu-id="74380-140">Wprowadzony wniosek urlopowy zawiera co najmniej jeden dzień z taką samą datą i typem urlopu, co istniejący oczekujący wniosek.</span><span class="sxs-lookup"><span data-stu-id="74380-140">The time off request entered contains one or more days with the same date and leave type as an existing pending request.</span></span> <span data-ttu-id="74380-141">Aby wprowadzić zmiany, wycofaj istniejący wniosek.</span><span class="sxs-lookup"><span data-stu-id="74380-141">Please recall the existing request to make changes.</span></span>
 - <span data-ttu-id="74380-142">Kod przyczyny „{ReasonCodeId}” nie ma zastosowania do żadnego typu urlopu we wniosku.</span><span class="sxs-lookup"><span data-stu-id="74380-142">Reason code '{ReasonCodeId}' doesn't apply to any of the leave types in the request.</span></span>
 - <span data-ttu-id="74380-143">Typ urlopu „{LeaveTypeId}” wymaga kodu przyczyny.</span><span class="sxs-lookup"><span data-stu-id="74380-143">Leave type '{LeaveTypeId}' requires a reason code.</span></span> <span data-ttu-id="74380-144">Wybierz odpowiedni typ i kod przyczyny.</span><span class="sxs-lookup"><span data-stu-id="74380-144">Select the appropriate type and reason code.</span></span>
 - <span data-ttu-id="74380-145">Wniosek urlopowy nie został pomyślnie przesłany.</span><span class="sxs-lookup"><span data-stu-id="74380-145">The time off was not submitted successfully.</span></span> <span data-ttu-id="74380-146">Wniosek urlopowy został zapisany jako wersja robocza wniosku.</span><span class="sxs-lookup"><span data-stu-id="74380-146">The time off has been saved as a draft request.</span></span>

## <a name="see-also"></a><span data-ttu-id="74380-147">Informacje dodatkowe</span><span class="sxs-lookup"><span data-stu-id="74380-147">See also</span></span>

- [<span data-ttu-id="74380-148">MyLeaveRequests — omówienie</span><span class="sxs-lookup"><span data-stu-id="74380-148">MyLeaveRequests overview</span></span>](hr-developer-api-myleaverequests-overview.md)
- [<span data-ttu-id="74380-149">Uwierzytelnianie</span><span class="sxs-lookup"><span data-stu-id="74380-149">Authentication</span></span>](hr-developer-api-authentication.md)