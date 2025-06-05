# Ex.No: 6  Implementation of Jumping  behaviour- Unity                                                                          
### REGISTER NUMBER : 212222220033
### AIM: 
To write a program to simulate the process of jumping in Unity.
### Algorithm:

1. Create a new 3D Unity project
2. Add a Plane
3. Right-click Hierarchy → 3D Object → Plane → Rename to Ground
4. Add a Cube (Player)
5. Right-click Hierarchy → 3D Object → Cube → Rename to Player
6. Set Position: (0, 0.5, 0)
7. Add a Rigidbody to the Player
8. With the Player selected: Inspector → Add Component → Rigidbody
9. Set Constraints > Freeze Rotation X, Z (optional for stability)
10.Create the Jump Script and Apply the Script Player
11.Run the game
Press Play
Press Spacebar to jump
Your cube should only jump when touching the ground

### Program 
```
using UnityEngine;

public class PlayerJump : MonoBehaviour
{
    private Rigidbody rb;
    public float jumpForce = 5f;
    private bool isGrounded;

    void Start()
    {
        rb = GetComponent<Rigidbody>();
    }

    void Update()
    {
        if (Input.GetKeyDown(KeyCode.Space) && isGrounded)
        {
            rb.AddForce(Vector3.up * jumpForce, ForceMode.Impulse);
            isGrounded = false;
        }
    }

    private void OnCollisionEnter(Collision collision)
    {
        if (collision.gameObject.CompareTag("Ground"))
        {
            isGrounded = true;
        }
    }
}
```
### Output:
### Initially player in air:
![435562714-002250ad-13a1-4514-bb5b-3143cee9aff2](https://github.com/user-attachments/assets/d31c12cb-386f-4f7a-adcc-32d72c2235e0)

### After player jumped:
![435562788-6c168f07-ddd3-48f0-aaf5-b2e7bb6fa33e](https://github.com/user-attachments/assets/b107d75d-b48b-4d80-8fd8-33885eb218df)

![435562822-243fbe45-5922-4e5f-a15c-8dbeb237a8bf](https://github.com/user-attachments/assets/e4627983-d575-437f-b636-779d4a68bab6)


### Result:
Thus the simple jumping behavior was implemented successfully.
