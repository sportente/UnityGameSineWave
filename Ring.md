# UnityGameSineWave
Wire Game with SineWave moving Spheres 

//Aim would be to move the ring up and down with the keyboard until it achieves the wire and then you should no more be able to move 
//the ring in that direction. 


using UnityEngine;
using System.Collections;

public class Ring : MonoBehaviour {

	public float speed=5f;
	private Rigidbody rb;



	// Use this for initialization
	void Start () {
		
		rb = GetComponent<Rigidbody> ();


	}



	void OnCollisionEnter(Collision collision) {


		if (collision.gameObject.name == "Sphere") {

      speed=0f; 

			Debug.Log ("Hit Sphere");

		}

	}



	void OnCollisionExit(Collision collisione) {

		if (collisione.gameObject.name == "Sphere") {

	    speed=5f; 
			Debug.Log ("No hit Sphere");
  

		}

	}



	void Update() {

		

			if (Input.GetKey (KeyCode.UpArrow)) {
				rb.position += Vector3.up * speed * Time.deltaTime; 

				//rb.AddForce (Vector3.up*speed*Time.deltaTime);

			}
			if (Input.GetKey (KeyCode.DownArrow)) {
				//rb.AddForce (Vector3.down*speed*Time.deltaTime);
				rb.position += Vector3.down * speed * Time.deltaTime; 

			}

		

	}
	

		}
