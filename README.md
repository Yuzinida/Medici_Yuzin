# Medici_Yuzin

# 게임 엔진의 특징
- 멀티플랫폼 빌드
- 모바일 빌드
  - 안드로이드
  - IOS
  
--------
public class Controller : MonoBehaviour
{
    private Camera arCamera;
    private RaycastHit hit;

    void Start()
    {
        arCamera = Camera.main;
    }

    void Update()
    {
        if (Input.GetMouseButtonDown(0))
        {
            Debug.Log("Touched");
        }

        if (Input.GetMouseButton(0))
        {
            Debug.Log($"Touching {Time.time}"); // $를 써서 { } 안에 있는 값을 치환해준다
            // Debug.Log("Touching" + Time.time);
        }
        Vector2 pos = Input.mousePosition; // 터치 좌표
        // 스크린 터치 좌표값을 3차원 ray로 생성하겠다..
        Ray ray = arCamera.ScreenPointToRay(pos);

        if (Input.GetMouseButtonDown(0)&& Physics.Raycast(ray, out hit, 10.0f, 1<<8))
        {
            hit.collider.GetComponent<Renderer>().material.color = Color.red;
        }

        if (Input.GetKeyDown(KeyCode.LeftArrow)) // 화살표 입력값
        {
            Debug.Log("왼쪽을 누름");
        }

        if (Input.GetKeyDown(KeyCode.RightArrow)) // 화살표 입력값
        {
            Debug.Log("오른쪽을 누름");
        }

    }
}



|제목|주제|
|---|---|
|컴포넌트|캄포넌트란?|
|컴포넌트|캄포넌트란?|
|컴포넌트|캄포넌트란?|
